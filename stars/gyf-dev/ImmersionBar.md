---
project: ImmersionBar
stars: 11453
description: android 4.4以上沉浸式状态栏和沉浸式导航栏管理，适配横竖屏切换、刘海屏、软键盘弹出等问题，可以修改状态栏字体颜色和导航栏图标颜色，以及不可修改字体颜色手机的适配，适用于Activity、Fragment、DialogFragment、Dialog，PopupWindow，一句代码轻松实现，以及对bar的其他设置，详见README。简书请参考：http://www.jianshu.com/p/2a884e211a62
url: https://github.com/gyf-dev/ImmersionBar
---

ImmersionBar -- android 4.4以上沉浸式实现
==================================

直接看效果图，建议下载demo体验，最下面有各个版本的效果图
------------------------------

使用（gyf替换为geyifeng）
------------------

> 3.1.1以上版本(mavenCentral)

// 基础依赖包，必须要依赖
implementation 'com.geyifeng.immersionbar:immersionbar:3.2.2'
// kotlin扩展（可选）
implementation 'com.geyifeng.immersionbar:immersionbar-ktx:3.2.2'
// fragment快速实现（可选）已废弃
implementation 'com.geyifeng.immersionbar:immersionbar-components:3.2.2'

> 3.0.0版本(jcenter)

// 基础依赖包，必须要依赖
implementation 'com.gyf.immersionbar:immersionbar:3.0.0'
// kotlin扩展（可选）
implementation 'com.gyf.immersionbar:immersionbar-ktx:3.0.0'
// fragment快速实现（可选）
implementation 'com.gyf.immersionbar:immersionbar-components:3.0.0'

版本说明
----

#### 点我查看版本说明

下载demo
------

#### 点我下载immersionBar-3.2.2.apk

关于全面屏与刘海
--------

#### 关于全面屏

在manifest加入如下配置，四选其一，或者都写

① 升级targetSdkVersion为25以上版本，现在基本都是25以上了，所以以下三个没有必要配置了

② 在manifest的Application节点中加入

   android:resizeableActivity="true"

③ 在manifest的Application节点中加入

   android:maxAspectRatio="2.4"

④ 在manifest的Application节点下加入

   <meta-data 
     android:name\="android.max\_aspect"
     android:value\="2.4" />

#### 关于刘海屏

在manifest的Application节点下加入，vivo和oppo没有找到相关配置信息

   <!--适配华为（huawei）刘海屏\-->
   <meta-data 
     android:name\="android.notch\_support" 
     android:value\="true"/>
   <!--适配小米（xiaomi）刘海屏\-->
   <meta-data
     android:name\="notch.config"
     android:value\="portrait|landscape" />

Api详解
-----

-   基础用法
    
    ImmersionBar.with(this).init();
    
-   高级用法(每个参数的意义)
    
     ImmersionBar.with(this)
                 .transparentStatusBar()  //透明状态栏，不写默认透明色
                 .transparentNavigationBar()  //透明导航栏，不写默认黑色(设置此方法，fullScreen()方法自动为true)
                 .transparentBar()             //透明状态栏和导航栏，不写默认状态栏为透明色，导航栏为黑色（设置此方法，fullScreen()方法自动为true）
                 .statusBarColor(R.color.colorPrimary)     //状态栏颜色，不写默认透明色
                 .navigationBarColor(R.color.colorPrimary) //导航栏颜色，不写默认黑色
                 .barColor(R.color.colorPrimary)  //同时自定义状态栏和导航栏颜色，不写默认状态栏为透明色，导航栏为黑色
                 .statusBarAlpha(0.3f)  //状态栏透明度，不写默认0.0f
                 .navigationBarAlpha(0.4f)  //导航栏透明度，不写默认0.0F
                 .barAlpha(0.3f)  //状态栏和导航栏透明度，不写默认0.0f
                 .statusBarDarkFont(true)   //状态栏字体是深色，不写默认为亮色
                 .navigationBarDarkIcon(true) //导航栏图标是深色，不写默认为亮色
                 .autoDarkModeEnable(true) //自动状态栏字体和导航栏图标变色，必须指定状态栏颜色和导航栏颜色才可以自动变色哦
                 .autoStatusBarDarkModeEnable(true,0.2f) //自动状态栏字体变色，必须指定状态栏颜色才可以自动变色哦
                 .autoNavigationBarDarkModeEnable(true,0.2f) //自动导航栏图标变色，必须指定导航栏颜色才可以自动变色哦
                 .flymeOSStatusBarFontColor(R.color.btn3)  //修改flyme OS状态栏字体颜色
                 .fullScreen(true)      //有导航栏的情况下，activity全屏显示，也就是activity最下面被导航栏覆盖，不写默认非全屏
                 .hideBar(BarHide.FLAG\_HIDE\_BAR)  //隐藏状态栏或导航栏或两者，不写默认不隐藏
                 .addViewSupportTransformColor(toolbar)  //设置支持view变色，可以添加多个view，不指定颜色，默认和状态栏同色，还有两个重载方法
                 .titleBar(view)    //解决状态栏和布局重叠问题，任选其一
                 .titleBarMarginTop(view)     //解决状态栏和布局重叠问题，任选其一
                 .statusBarView(view)  //解决状态栏和布局重叠问题，任选其一
                 .fitsSystemWindows(true)    //解决状态栏和布局重叠问题，任选其一，默认为false，当为true时一定要指定statusBarColor()，不然状态栏为透明色，还有一些重载方法
                 .supportActionBar(true) //支持ActionBar使用
                 .statusBarColorTransform(R.color.orange)  //状态栏变色后的颜色
                 .navigationBarColorTransform(R.color.orange) //导航栏变色后的颜色
                 .barColorTransform(R.color.orange)  //状态栏和导航栏变色后的颜色
                 .removeSupportView(toolbar)  //移除指定view支持
                 .removeSupportAllView() //移除全部view支持
                 .navigationBarEnable(true)   //是否可以修改导航栏颜色，默认为true
                 .navigationBarWithKitkatEnable(true)  //是否可以修改安卓4.4和emui3.x手机导航栏颜色，默认为true
                 .navigationBarWithEMUI3Enable(true) //是否可以修改emui3.x手机导航栏颜色，默认为true
                 .keyboardEnable(true)  //解决软键盘与底部输入框冲突问题，默认为false，还有一个重载方法，可以指定软键盘mode
                 .keyboardMode(WindowManager.LayoutParams.SOFT\_INPUT\_ADJUST\_RESIZE)  //单独指定软键盘模式
                 .setOnKeyboardListener(new OnKeyboardListener() {    //软键盘监听回调，keyboardEnable为true才会回调此方法
                       @Override
                       public void onKeyboardChange(boolean isPopup, int keyboardHeight) {
                           LogUtils.e(isPopup);  //isPopup为true，软键盘弹出，为false，软键盘关闭
                       }
                  })
                 .setOnNavigationBarListener(onNavigationBarListener) //导航栏显示隐藏监听，目前只支持华为和小米手机
                 .setOnBarListener(OnBarListener) //第一次调用和横竖屏切换都会触发，可以用来做刘海屏遮挡布局控件的问题
                 .addTag("tag")  //给以上设置的参数打标记
                 .getTag("tag")  //根据tag获得沉浸式参数
                 .reset()  //重置所以沉浸式参数
                 .init();  //必须调用方可应用以上所配置的参数
    

在Activity中实现沉浸式
---------------

-   java用法
    
     ImmersionBar.with(this).init();
    
-   kotlin用法
    
     immersionBar {
         statusBarColor(R.color.colorPrimary) 
         navigationBarColor(R.color.colorPrimary)
     }
    

在Fragment中实现沉浸式
---------------

#### 在Fragment使用ImmersionBar

-   第一种，fragment如果配合viewpager2使用的话，并且使用了Behavior指定了BEHAVIOR\_RESUME\_ONLY\_CURRENT\_FRAGMENT，直接在fragment的onResume里直接实现沉浸式
-   第二种，当使用show()和hide()来控制Fragment显示隐藏的时候，直接在fragment的onResume与onHiddenChanged（参数hidden为false）方法里实现沉浸式
-   第三种（废弃），你的Fragment直接继承SimpleImmersionFragment或者ImmersionFragment类，在initImmersionBar方法中实现沉浸式代码，只有当immersionBarEnabled返回为true才可以走initImmersionBar方法哦，不过immersionBarEnabled默认返回已经为true了，如果当前Fragment不想走沉浸式方法，请将immersionBarEnabled设置为false
-   第四种（废弃），如果你的Fragment不能继承SimpleImmersionFragment或者ImmersionFragment类，请参考SimpleImmersionFragment实现SimpleImmersionOwner接口，或者参考ImmersionFragment实现ImmersionOwner接口

#### 在Activity使用ImmersionBar

-   第一种，当结合viewpager2使用的时候，请使用viewpager2的registerOnPageChangeCallback的方法监听沉浸式
-   第二种，当结合viewpager使用的时候，请使用viewpager的addOnPageChangeListener的方法监听沉浸式，参考demo中FragmentThreeActivity这个类
-   第三种，当使用show()和hide()来控制Fragment显示隐藏的时候，请在tab切换的时候使用ImmersionBar，参考demo中FragmentFourActivity这个类

#### 使用Fragment第三方框架Fragmentation实现沉浸式

-   参考demo中FragmentFiveActivity和BaseFiveFragment这个类

在Dialog中实现沉浸式，具体实现参考demo
------------------------

-   ①结合dialogFragment使用，可以参考demo中的BaseDialogFragment这个类
    
        ImmersionBar.with(this).init();
    
-   ②其他dialog，关闭dialog的时候必须调用销毁方法
    
        ImmersionBar.with(this, dialog).init();
    
    销毁方法：
    
    java中
    
        ImmersionBar.destroy(this, dialog);
    
    kotlin中
    
        destroyImmersionBar(dialog)
    

在PopupWindow中实现沉浸式，具体实现参考demo
-----------------------------

重点是调用以下方法，但是此方法会导致有导航栏的手机底部布局会被导航栏覆盖，还有底部输入框无法根据软键盘弹出而弹出，具体适配请参考demo。

    popupWindow.setClippingEnabled(false);

状态栏与布局顶部重叠解决方案，六种方案根据不同需求任选其一
-----------------------------

-   ① 使用dimen自定义状态栏高度，不建议使用，因为设备状态栏高度并不是固定的
    
    在values-v19/dimens.xml文件下
    
        <dimen name\="status\_bar\_height"\>25dp</dimen\>
    
    在values/dimens.xml文件下
    
        <dimen name\="status\_bar\_height"\>0dp</dimen\>
    
    然后在布局界面添加view标签，高度指定为status\_bar\_height
    
       <LinearLayout xmlns:android\="http://schemas.android.com/apk/res/android"
           xmlns:app\="http://schemas.android.com/apk/res-auto"
           android:layout\_width\="match\_parent"
           android:layout\_height\="match\_parent"
           android:background\="@color/darker\_gray"
           android:orientation\="vertical"\>
       
           <View
               android:layout\_width\="match\_parent"
               android:layout\_height\="@dimen/status\_bar\_height"
               android:background\="@color/colorPrimary" />
       
           <android.support.v7.widget.Toolbar
               android:layout\_width\="match\_parent"
               android:layout\_height\="wrap\_content"
               android:background\="@color/colorPrimary"
               app:title\="方法一"
               app:titleTextColor\="@android:color/white" />
       </LinearLayout\>
    
-   ② 使用系统的fitsSystemWindows属性，使用该属性不会导致输入框与软键盘冲突问题，不要再Fragment使用该属性，只适合纯色状态栏
    
        <LinearLayout xmlns:android\="http://schemas.android.com/apk/res/android"
            android:layout\_width\="match\_parent"
            android:layout\_height\="match\_parent"
            android:orientation\="vertical"
            android:fitsSystemWindows\="true"\>
        </LinearLayout\>
    
    然后使用ImmersionBar时候必须指定状态栏颜色
    
        ImmersionBar.with(this)
             .statusBarColor(R.color.colorPrimary)
             .init();
    
    -   注意：ImmersionBar一定要在设置完布局以后使用，
-   ③ 使用ImmersionBar的fitsSystemWindows(boolean fits)方法，只适合纯色状态栏
    
        ImmersionBar.with(this)
            .fitsSystemWindows(true)  //使用该属性,必须指定状态栏颜色
            .statusBarColor(R.color.colorPrimary)
            .init();
    
-   ④ 使用ImmersionBar的statusBarView(View view)方法，可以用来适配渐变色状态栏、侧滑返回
    
    在标题栏的上方增加View标签，高度指定为0dp
    
        <LinearLayout xmlns:android\="http://schemas.android.com/apk/res/android"
               xmlns:app\="http://schemas.android.com/apk/res-auto"
               android:layout\_width\="match\_parent"
               android:layout\_height\="match\_parent"
               android:background\="@color/darker\_gray"
               android:orientation\="vertical"\>
           
               <View
                   android:layout\_width\="match\_parent"
                   android:layout\_height\="0dp"
                   android:background\="@color/colorPrimary" />
           
               <android.support.v7.widget.Toolbar
                   android:layout\_width\="match\_parent"
                   android:layout\_height\="wrap\_content"
                   android:background\="@color/colorPrimary"
                   app:title\="方法四"
                   app:titleTextColor\="@android:color/white" />
        </LinearLayout\>
    
    然后使用ImmersionBar的statusBarView方法，指定view就可以啦
    
         ImmersionBar.with(this)
               .statusBarView(view)
               .init();
         //或者
         //ImmersionBar.setStatusBarView(this,view);
    
-   ⑤ 使用ImmersionBar的titleBar(View view)方法，原理是设置paddingTop，可以用来适配渐变色状态栏、侧滑返回
    
             ImmersionBar.with(this)
                   .titleBar(view) //可以为任意view，如果是自定义xml实现标题栏的话，标题栏根节点不能为RelativeLayout或者ConstraintLayout，以及其子类
                   .init();
             //或者
             //ImmersionBar.setTitleBar(this, view);
    
-   ⑥ 使用ImmersionBar的titleBarMarginTop(View view)方法，原理是设置marginTop，只适合纯色状态栏
    
             ImmersionBar.with(this)
                   .titleBarMarginTop(view)  //可以为任意view
                   .statusBarColor(R.color.colorPrimary)  //指定状态栏颜色,根据情况是否设置
                   .init();
             //或者使用静态方法设置
             //ImmersionBar.setTitleBarMarginTop(this,view);
    

解决EditText和软键盘的问题
-----------------

-   第一种方案
    
        ImmersionBar.with(this)
                    .keyboardEnable(true)  //解决软键盘与底部输入框冲突问题
                //  .keyboardEnable(true, WindowManager.LayoutParams.SOFT\_INPUT\_STATE\_ALWAYS\_VISIBLE
                //                        | WindowManager.LayoutParams.SOFT\_INPUT\_ADJUST\_RESIZE)  //软键盘自动弹出
                    .init();
    
-   第二种方案 不使用keyboardEnable方法，只需要在布局的根节点（最外层节点）加上android:fitsSystemWindows="true"属性即可，只适合纯色状态栏

当白色背景状态栏遇到不能改变状态栏字体为深色的设备时，解决方案
-------------------------------

      ImmersionBar.with(this)
                  .statusBarDarkFont(true, 0.2f) //原理：如果当前设备支持状态栏字体变色，会设置状态栏字体为黑色，如果当前设备不支持状态栏字体变色，会使当前状态栏加上透明度，否则不执行透明度
                  .init();

状态栏和导航栏其它方法
-----------

-   public static boolean hasNavigationBar(Activity activity)
    
    判断是否存在导航栏
    
-   public static int getNavigationBarHeight(Activity activity)
    
    获得导航栏的高度
    
-   public static int getNavigationBarWidth(Activity activity)
    
    获得导航栏的宽度
    
-   public static boolean isNavigationAtBottom(Activity activity)
    
    判断导航栏是否在底部
    
-   public static int getStatusBarHeight(Activity activity)
    
    获得状态栏的高度
    
-   public static int getActionBarHeight(Activity activity)
    
    获得ActionBar的高度
    
-   public static boolean hasNotchScreen(Activity activity)
    
    是否是刘海屏
    
-   public static boolean getNotchHeight(Activity activity)
    
    获得刘海屏高度
    
-   public static boolean isSupportStatusBarDarkFont()
    
    判断当前设备支不支持状态栏字体设置为黑色
    
-   public static boolean isSupportNavigationIconDark()
    
    判断当前设备支不支持导航栏图标设置为黑色
    
-   public static void hideStatusBar(Window window)
    
    隐藏状态栏
    

混淆规则(proguard-rules.pro)
------------------------

#### 3.1.1以上版本无需混淆

#### 3.0.0以下版本混淆规制

```
 -keep class com.gyf.immersionbar.* {*;} 
 -dontwarn com.gyf.immersionbar.**
```

问题汇总
----

#### 点我问题汇总

效果图
---

#### 说明

-   这是状态栏
-   这是导航栏（有些手机没有导航栏）

#### 动态图

-   android 6.0 有导航栏效果

-   android 4.4 有导航栏效果

-   android 4.4 没有导航栏效果

特别鸣谢
----

-   感谢zhangzhen92、 yutouxiansheng 、MrWhhh提供测试

联系我
---

-   QQ群 314360549（问题交流）
