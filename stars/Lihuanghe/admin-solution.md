---
project: admin-solution
stars: 1
description: admin-solution 是一个权限管理系统模板. 采用 Vue + ElementUI + SpringBoot + Shiro + MySQL 实现
url: https://github.com/Lihuanghe/admin-solution
---

admin-solution
--------------

admin-solution 是一个权限管理系统模板.

-   前端基于 vue-element-admin 进行二次开发.
-   后端采用Java语言, 基于SpringBoot, Shiro, MySQL实现

             |
             |前端权限控制 --> 动态从后端请求路由
权限控制 -->  |
             |后端权限控制 --> 进行接口调用访问控制
             |

### token存储

vue-element-admin 默认是读取body里面的token

  login({ commit }, userInfo) {
    const { username, password } \= userInfo
    return new Promise((resolve, reject) \=> {
      login({ username: username.trim(), password: password }).then(response \=> {
        const { data } \= response
        commit('SET\_TOKEN', data.token)
        setToken(data.token)
        resolve()
      }).catch(error \=> {
        reject(error)
      })
    })

然后使用该token与后端进行权限验证

service.interceptors.request.use(
  config \=> {
    // do something before request is sent
    return config
  },
  error \=> {
    // do something with request error
    console.log(error) // for debug
    return Promise.reject(error)
  }
)

现在修改成, 后端直接将token存储在cookie header里, 并且设置为httponly

@Configuration
public class ShiroConfig {

    // ... 其他设置
    
    public SimpleCookie buildCookie() {
        SimpleCookie simpleCookie = new SimpleCookie(TOKEN\_NAME);
        simpleCookie.setPath("/");
        // 对服务器生成的TOKEN设置 HttpOnly 属性. 前端无法读写该TOKEN, 提供系统安全, 防止XSS攻击
        simpleCookie.setHttpOnly(true);
        // 设置浏览器关闭时失效此Cookie
        simpleCookie.setMaxAge(-1);
       
        return simpleCookie;
    }

}

前端在某些场景中仍然需要做token之类的校验, cookie里的token也取不到, 所以在登录接口的应答报文体里也返回了一个token, 代表登录成功了. 该token只是前端做使用, 不参与后端的校验工作.

### 前端路由

前端路由存储在后端数据库里, 用户登录时向后端请求路由json, 然后前端进行动态添加

const actions \= {
  generateRoutes({ commit }, roles) {
    return new Promise(resolve \=> {
      getUserFrontendPermissions().then(response \=> {
        
        let routeNodes \= response.data.routeNodes
        importComponent(routeNodes)
        
        commit('SET\_ROUTES', routeNodes)
        resolve(routeNodes)
      })
      
    })
  }
}

function importComponent(routeNodes) {

  for(var rn of routeNodes) {
    if(rn.component \== "Layout") {
      rn.component \= Layout
    } else {
      let componentPath \= rn.component
      rn.component \= () \=> import(\`@/views/${componentPath}\`)
    }
   
    if(rn.children && rn.children.length \> 0) {
      importComponent(rn.children)
    }
  }
}

主要的函数就是`importComponent(routeNodes)`, 采用递归的方式import组件.

> 这里要说明一下, webpack 编译es6 动态引入 import() 时不能传入变量, 但一定要用变量的时候，可以通过字符串模板来提供部分信息给webpack；例如import(`./path/${myFile}`), 这样编译时会编译所有./path下的模块. 参考在vue中import()语法为什么不能传入变量?

### 后端权限验证

后端采用shiro进行权限验证, 这是一个非常有趣的框架, 代码写的结构清晰简单明了 👍

@Configuration
public class ShiroConfig {

   /\*\*
    \* 设置接口权限验证, 目前只针对api接口进行权限验证
    \*
    \* @param securityManager
    \* @return
    \*/
   @Bean(name = "shiroFilter")
   public ShiroFilterFactoryBean shiroFilter(SecurityManager securityManager) {
       LOGGER.info("start shiroFilter setting");

       ShiroFilterFactoryBean shiroFilterFactoryBean = new ShiroFilterFactoryBean();
       shiroFilterFactoryBean.setSecurityManager(securityManager);

       shiroFilterFactoryBean.setLoginUrl("/");
       shiroFilterFactoryBean.setSuccessUrl("/#/dashboard");
       shiroFilterFactoryBean.setUnauthorizedUrl("/403");

       Map<String, String\> filterChainDefinitionMap = new LinkedHashMap<>();

       Map<String, Filter\> filtersMap = new LinkedHashMap<>();
       filtersMap.put("apiAccessControlFilter", new ApiAccessControlFilter());
       shiroFilterFactoryBean.setFilters(filtersMap);

       filterChainDefinitionMap.put("/static/\*\*", "anon");
       filterChainDefinitionMap.put("/#/login/\*\*", "anon");
       filterChainDefinitionMap.put("/api/user/auth/login", "anon");
       filterChainDefinitionMap.put("/logout", "logout");
       filterChainDefinitionMap.put("/api/\*\*", "apiAccessControlFilter");
       filterChainDefinitionMap.put("/\*\*", "logFilter");
       filterChainDefinitionMap.put("/\*\*", "authc");

       shiroFilterFactoryBean.setFilterChainDefinitionMap(filterChainDefinitionMap);

       LOGGER.info("shirFilter config fineshed");
       return shiroFilterFactoryBean;
   }
}

目前是只对`/api/**` 接口进行了权限校验设置

public class ApiAccessControlFilter extends AccessControlFilter {

    private static final Logger LOGGER = LoggerFactory.getSystemLogger(ApiAccessControlFilter.class);

    @Override
    protected boolean isAccessAllowed(ServletRequest request, ServletResponse response, Object mappedValue) throws Exception {

        // 开发环境中, 如果是OPTIONS预检请求则直接返回true TODO 这里想办法做的更加优雅些, 目前就是个补丁
        if (!SpringUtil.isInProduction()
                && request instanceof HttpServletRequest
                && "OPTIONS".equals(((HttpServletRequest) request).getMethod())) {
            return true;
        }

        HttpServletRequest httpServletRequest = (HttpServletRequest) request;

        Subject subject = SecurityUtils.getSubject();

        boolean isAuthenticated = subject.isAuthenticated();
        boolean isPermitted = subject.isPermitted(httpServletRequest.getRequestURI());

        LOGGER.info("鉴权完成, isPermitted:{}, isAuthenticated:{}", isPermitted, isAuthenticated);

        return isPermitted && isAuthenticated;
    }

    private void trySetUserLog() {
        LoggerLocalCache.INSTANCE.setUser(UserUtil.getCurrentUserName());
    }

    @Override
    protected boolean onAccessDenied(ServletRequest request, ServletResponse servletResponse) throws Exception {
        LOGGER.info("访问被拒绝");
        Response response = ResponseCode.AUTH\_FAIL.build();

        String result = JSON.toJSONString(response);
        servletResponse.getOutputStream().write(result.getBytes("UTF8"));
        servletResponse.flushBuffer();

        return false;
    }
}

### 跨域问题

前端开发过程中会涉及到跨域问题, 因此需要前端和后端一起修改

前端

if (process.env.NODE\_ENV \=== 'development') {
 service.defaults.baseURL \= 'http://localhost:9900/'
 service.defaults.withCredentials \= true
}

后端

@Configuration
public class ShiroConfig {

   @Bean
   public CorsFilter corsFilter() {
       // CORS配置信息
       CorsConfiguration config = new CorsConfiguration();

       if (!SpringUtil.isInProduction(applicationContext)) {
           LOGGER.info("进行非生产模式CORS配置");

           config.addAllowedOrigin("\*");

           config.setAllowCredentials(true);

           config.addAllowedMethod("\*");

           config.addAllowedHeader("\*");
           config.addExposedHeader("Set-Cookie");

       }

       UrlBasedCorsConfigurationSource configSource = new UrlBasedCorsConfigurationSource();
       configSource.registerCorsConfiguration("/\*\*", config);
       return new CorsFilter(configSource);
   }
}

这样设置在get请求中没问题, 但是在post请求时会先对请求进行预检发送OPTIONS请求, 因此在上面`权限验证`中的`ApiAccessControlFilter`中进行了相关设置

 if (!SpringUtil.isInProduction()
                && request instanceof HttpServletRequest
                && "OPTIONS".equals(((HttpServletRequest) request).getMethod())) {
            return true;
        }

这不是一种好的解决方案, 目前算是一种补丁吧, 后期想想更好的解决方案.

### 权限关系

-   `User` 表存储用户登录信息
-   `Role` 表存储角色
-   `UserRoleRelation` 表存储用户角色关系
-   `BackendPermission` 表存储后端权限(当服务器启动时会将所有路径都自动保存在该表里)
-   `RoleBackendPermissionRelation` 表存储角色拥有的后端权限
-   `FrontendPermission` 表存储前端路由信息.
-   `RoleFrontendPermissionRelation` 表存储角色拥有的前端路由信息

### HTTP请求日志

为了在开发过程中能够比较方便的排查问题, 因此在`HttpTraceLogFilter`中将每次请求报文与应答报文都进行了打印(生产环境可以选择关闭)

```
2020-04-02 11:37:51.963 [http-nio-9900-exec-2] INFO  c.w.a.config.HttpTraceLogFilter(162) - [admin, /api/user/authority/getUserFrontendPermissions] Http 请求日志: HttpTraceLog{
     method='GET',
     path='/api/user/authority/getUserFrontendPermissions',
     parameterMap='{}',
     timeTaken=17,
     time='2020-04-02T11:37:51.962',
     status=200,
     requestHeaders='
            host: localhost:9900
            connection: keep-alive
            accept: application/json, text/plain, */*
            sec-fetch-dest: empty
            user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36
            dnt: 1
            sec-fetch-site: same-origin
            sec-fetch-mode: cors
            referer: http://localhost:9900/
            accept-encoding: gzip, deflate, br
            accept-language: zh-CN,zh;q=0.9,en;q=0.8
            cookie: TTOKEN=0bbfbdca-40e5-4ee3-b19e-37d9b114cb47; frontend-token=undefined',
     requestBody='',
     responseHeaders='
            Vary: Origin
            Vary: Origin
            Vary: Origin',
     responseBody='{"code":20000,"message":"成功","data":{"routeNodes":[{"name":"权限配置","path":"/permission","component":"Layout","redirect":"/permission/frontend","meta":{"title":"权限配置","icon":"example"},"children":[{"name":"前端权限","path":"frontend","component":"permission/frontend/index","redirect":null,"meta":{"title":"前端权限","icon":"table"},"children":[]},{"name":"后端权限","path":"backend","component":"permission/backend/index","redirect":null,"meta":{"title":"后端权限","icon":"table"},"children":[]}]}]}}',}

```
