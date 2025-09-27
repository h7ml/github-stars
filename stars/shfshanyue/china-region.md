---
project: china-region
stars: 76
description: 根据国家标准《中华人民共和国行政区划代码》即 GB2260 标准制定，用以查看各个省地县的行政区划代码，并支持多级联动查询
url: https://github.com/shfshanyue/china-region
---

中国行政区划代码
========

根据国家标准《中华人民共和国行政区划代码》即 GB2260 标准制定，用以查看各个省地县的行政区划代码，并支持多级联动查询

1.  丰富的 API，满足多种级联查询
2.  较小的 npm 包体积

版本
--

版本最近更新于 20210812，爬取数据为 http://www.mca.gov.cn/article/sj/xzqh/2020/20201201.html

安装
--

### npm

$ npm install china-region

import { getProvinces } from 'china-region'

// 仅仅获取所有行政区域的 JSON 数据
import province from 'china-region/region.json'

// 仅仅获取省份的 JSON 数据
import province from 'china-region/province.json'

### CDN

你可以在 CDN 中直接使用它，并调用 API。

<script src\="https://cdn.jsdelivr.net/npm/china-region"\></script\>
<script\>
  const provinces \= cn.getProvinces()
</script\>

### 在线调试

你可以在 china-region 中，打开控制台，在线尝试该 API。

API
---

const cn \= require('china-region')

const code \= cn.getCodeByProvinceName('晋')

const cities \= cn.getPrefectures(code)
// \[
//   { code: '140100', name: '太原市' },
//   { code: '140200', name: '大同市' },
//   { code: '140300', name: '阳泉市' },
//   { code: '140400', name: '长治市' },
//   { code: '140500', name: '晋城市' },
//   { code: '140600', name: '朔州市' },
//   { code: '140700', name: '晋中市' },
//   { code: '140800', name: '运城市' },
//   { code: '140900', name: '忻州市' },
//   { code: '141000', name: '临汾市' },
//   { code: '141100', name: '吕梁市' }
// \]

### cn.getCodeByProvinceName(name)

根据升级行政区名称或简称获取行政区划代码

//=> '140000'
cn.getCodeByProvinceName('山西省')

// 通过二字省名来定位省份
//=> '140000'
cn.getCodeByProvinceName('山西')

// 通过省简称来定位省份
//=> '140000'
cn.getCodeByProvinceName('晋')

### cn.info(code)

返回某个行政区号代表的行政区

// { name: '洪洞县', code: '141024', prefecture: '临汾市', province: '山西省' }
cn.info('141024')

// { name: '山西省', code: '140000', prefecture: null, province: null }
cn.info('140000')

### cn.getAllRegions()

返回中国所有的各级行政区

cn.getAllRegions()

### cn.getProvinces()

返回中国所有的省级行政区

cn.getProvinces()

// \[
//   '京', '津', '冀', '晋', '蒙',
//   '辽', '吉', '黑', '沪', '苏',
//   '浙', '皖', '闽', '赣', '鲁',
//   '豫', '鄂', '湘', '粤', '桂',
//   '琼', '渝', '川', '贵', '云',
//   '藏', '陕', '甘', '青', '宁',
//   '新', '台', '港', '澳'
// \]
cn.getProvinces().map(x \=> x.alias)

### cn.getPrefectures(code)

返回中国/某省级行政区下所有的地级行政区

code 指行政区代码，code 为空时返回中国所有的地级行政区，不为空时返回该省级行政区的所有地级行政区

// 列出中国所有的地级行政区
cn.getPrefectures()

// 以下均列出 10 所代表省下辖的所有地级行政区
cn.getPrefectures('100000')
cn.getPrefectures('101000')
cn.getPrefectures('101010')

### cn.getCounties(code)

返回中国/某省级行政区/某地级行政区下所有的县级行政区

code 指行政区代码，code 为空时返回中国所有的县级行政区，不为空时返回该省/市级行政区的所有地级行政区

// 列出中国所有的县级行政区
cn.getCounties()

// 列出 10 所代表省下辖的所有县级行政区
cn.getCounties('100000')

// 列出 1010 所代表地下辖的所有县级行政区
cn.getCounties('101000')

### cn.getSpecialConties(code)

返回中国/某省级行政区下所有的省直管县。如海南省的各县和县级市、湖北省的仙桃市、潜江市、天门市、神农架林区、河南省的济源市、新疆的数个由自治区和新疆兵团双重领导的县级市等

code 指行政区代码，code 为空时返回中国所有的县级行政区，不为空时返回该省/市级行政区的所有地级行政区

// 列出中国所有的省直管县
cn.getSpecialCounties()

// 列出 10 所代表省下辖的所有省直管县
cn.getSpecialCounties('100000')

术语
--

> 关于行政区级别翻译参考知乎两篇关于地名翻译的文章
> 
> -   乡、镇、屯、自然村、组、生产队、自治区等名词有官方的英语翻译吗？
> -   地名如何翻译

-   `province`，省级行政区，包括直辖市、省、自治区、特别行政区。
-   `prefecture`，地级行政区，包括地级市、地区、自治州、盟。
-   `county`，县级行政区，包括市辖区、县级市、县、自治县、旗、自治旗、特区、林区。
-   `specialCounty`，省直管县级行政区，如湖北的仙桃、潜江与天门

数据获取
----

行政代码在国家标准《中华人民共和国行政区划代码》即 GB2260 的标准下制定，可以在民政部统计数据中查询。

-   2020年中华人民共和国行政区划代码

相关仓库
----

-   china-area-data
-   province-city-china
-   GB2260
