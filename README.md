
## 项目描述

#### 样式

- 项目需要全屏展示（按 F11）。

- 项目部分区域使用了全局注册方式，增加了打包体积，在实际运用中请使用 **按需引入**。

- 项目环境：Vite、Echarts、pnpm、loadsh、countup.js、 axios、mock、Vue3、Pinia、Vue-router。


##  2、主要文件介绍

| 文件              | 作用/功能                                                    |
| ----------------- | ------------------------------------------------------------ |
| main.js           | 主目录文件，引入 Echart/DataV 等文件                         |
| utils             | 工具函数与 mixins 函数等                                     |
| views/ home.vue   | 项目主结构                                                   |
| views/其余文件    | 界面各个区域组件（按照位置来命名）                           |
| assets            | 静态资源目录，放置 logo 与背景图片                           |
| assets / css/     | 通用 CSS 文件，全局项目快捷样式调节                          |
| components/echart | 所有 echart 图表（按照位置来命名）                           |
| common/...        | 全局封装的 ECharts 和 flexible 插件代码（适配屏幕尺寸）      |
| api/api.js        | 接口封装文件                                                 |
| mock              | 模拟数据接口地址                                             |

###  

## 使用介绍

### 安装

```npm
npm install   
```
### 启动

```npm
npm run dev
```

### 取消mock模拟数据

```javascript
// src\main.ts文件
把下面两行代码注释掉就可以了。
import { mockXHR } from "@/mock/index";
mockXHR()
```

## 

## 公用组件

封装了除面条外个别用到的组件

### 自适应缩放组件

#### 注意

采用Scale方式，会自动给组件父元素添加overflow:hidden 

- vw vh方案：
实现方式：
按照设计稿的尺寸，将px按比例计算转为vw和vh
优点：1.可以动态计算图表的宽高，字体等，灵活性较高 
2.当屏幕比例跟 ui 稿不一致时，不会出现两边留白情况
缺点：每个图表都需要单独做字体、间距、位移的适配，比较麻烦
