# Moy 快速入门

## 1. 环境准备和获取去资源

### 1.1单独开发理解原理

- 效果图

  ![kuaisu](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/%E5%BF%AB%E9%80%9F%E5%BC%80%E5%8F%91/kuaisu.gif)

  ​

### 1.2 引入资源分析

- 1.2.1引入 css 文件

```
<link rel="stylesheet" href="http://design.yyuap.com/static/uploader/css/webuploader.css">

 <link rel="stylesheet" href="http://design.yyuap.com/static/uui/latest/css/font-awesome.css">

 <link rel="stylesheet" type="text/css" href="http://design.yyuap.com/static/uui/latest/css/u.css">

 <link rel="stylesheet" type="text/css" href="http://design.yyuap.com/static/uui/latest/css/tree.css">

 <link rel="stylesheet" type="text/css" href="http://design.yyuap.com/static/uui/latest/css/grid.css">

```

- 1.2.2引入 js 文件

```
<script src="http://design.yyuap.com/static/jquery/jquery-1.11.2.js"></script>
<script src="http://design.yyuap.com/static/uploader/js/webuploader.js"></script>
<script src="http://design.yyuap.com/static/knockout/knockout-3.2.0.debug.js"></script>
<script src="http://design.yyuap.com/static/uui/latest/js/u-polyfill.js"></script>
<script src="http://design.yyuap.com/static/uui/latest/js/u.js"></script>
<script src="http://design.yyuap.com/static/uui/latest/js/u-tree.js"></script>
<script src="http://design.yyuap.com/static/uui/latest/js/u-grid.js"></script>
<script src="http://design.yyuap.com/static/requirejs/require.debug.js"></script>
```

- 1.2.3 html 部分编写

```
 <div class="u-container-fluid u-widget-bg">
    <div class="u-row">
      <div class="u-col-md-12">
        <div class="u-widget  u-widget-right">
          <div class="u-widget-heading">
          <!-- 定义Title -->
            <h3 class="u-widget-title">快速入门案例</h3>
            <div class="button_out">
            	<!-- 定义操作数据按钮 class 引用平台封装 u.css 样式 data-bind 绑定事件-->
              <button class="u-button u-button-success " data-bind="click:event.addClick">增加</button>
              <button class="u-button u-button-danger" data-bind="click:event.delClick">删除</button>
            </div>
          </div>
          <div class="u-widget-body">
          <!-- 定义 复杂表格grid 定义 id 数据模型 u-meta 此处注意 type 一定是 grid和 data 为自己定义的数据模型 dataTable-->
            <div id="gridTest" u-meta='{"id":"grid","type":"grid","data":"dataTable","columnMenu":false,"canDrag":false,"sortable":false,"canSwap":false}'>
              <div options='{"field":"name","dataType":"String","title":"姓名"}'></div>
              <div options='{"field":"time","dataType":"time","title":"日期"}'></div>
              <div options='{"field":"distance","dataType":"String","title":"距离"}'></div>
              <div options='{"field":"currency","dataType":"String","title":"金额"}'></div>
              <div options='{"field":"currency","dataType":"String","title":"金额"}'></div>
              <div options='{"field":"currency","dataType":"String","title":"金额"}'></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
```

- 1.2.4 页面逻辑部分代码

```
<script>
  //定义数据模型
  viewModel = {
    dataTable: new u.DataTable({
      meta: {
        "name": "",
        "time": "",
        "distance": "",
        "currency": ""
      }
    }, this),
    event: {
      addClick: function () {
        console.log('添加数据')
        getDate('https://mock.yonyoucloud.com/mock/276/moyTest/addlist')
      },
      delClick: function () {
        console.log('删除数据');
        getDate('https://mock.yonyoucloud.com/mock/276/moyTest/dellist')
      }
    }
  };
  //初始化页面结构并写入页面
  var app = new u.createApp();
  app.init(viewModel);
  //获取数据定义数据
  var getDate = function (url) {
    $.ajax({
      url: url,
      success: function (data) {
        console.log('获取数据成功')
        viewModel.dataTable.removeAllRows();
        viewModel.dataTable.setData(data);
      },
      error: function (error) {
        console.log(error.msg)
      }
    })
  }
  getDate('https://mock.yonyoucloud.com/mock/276/moyTest/userlist')
</script>
```

## 2 快速初始化项目及预览效果

### 2.1 使用 uba 初始化项目工程

1. 先安装[uba](https://github.com/iuap-design/tinper-uba)，并确保版本是2.0.4或以上(mac环境需加上`sudo`)

   ```
   $ sudo npm install uba -g 
   $ uba -v
   Version : 2.0.4
   ```

2. 然后创建应用，[uba详细使用文档](https://github.com/iuap-design/tinper-uba/blob/master/README_zh-CN.md)：

   ```
   $ uba init
   ```

3. 根据上下键移动选择`uba-boilerplate-manage-init - 后台管理系统的示例工程(初始化)` ，并且输入自己的项目名称比如：`manage-demo` ps：`uba-boilerplate-manage - 后台管理系统的示例工程` 是上面工程根据此文档完工后的示例工程，可以直接使用

4. 进入应用，启动项目

   ```
   $ cd manage-demo
   $ npm run start
   ```

5. 访问项目首页，<http://localhost:8080/>

   uba初始化演示：

   ![uba_init](https://design.yonyoucloud.com/static/img/tinper-docs/222.gif)

### 2.2 实现路由切换页面展示

1. 注册路由：在`router/router.js`文件中替换为如下代码：

   ```
   define(function() {
       return [{
           name: "/mainPage/main"
       }, {
           name: "/cardtable/cardtable"
       }]
   });
   ```

2. 在左侧栏添加入口：在`index.html`中加入新增应用管理入口代码：

   ```
   <ul class="nav-menu height-full" id="menu">
     <!-- 原有代码请勿拷贝 -->
     <li class='nav-li'>
       ...
     </li>
     <!-- 新增应用管理入口代码 begin -->
     <li class='nav-li'>
       <!-- a标签地址要指向到你想去的页面的路由地址 -->
       <a href="#cardtable/cardtable">
         <i class="uf uf-4square-3"></i>
         <span class="nav-title">应用管理</span>
       </a>
     </li>
     <!-- 新增应用管理入口代码 end -->
   </ul>
   ```

3. 在首页添加入口：在`pages/mainPage/main.html`中加入新增应用管理代码：

   ```
   <div class="u-row bottom-layout margin-0">
     <!-- 原有代码请勿拷贝 -->
     <div class="u-col-xs-6 u-col-md-3 content">
       ...
     </div>
     <!--新增应用管理 begin -->
     <div class="u-col-xs-6 u-col-md-3 content">
       <a href="#cardtable/cardtable">
         <div class="u-form-group">
           <div class="u-col-xs-12 content-svg">
             <img src="./static/applimanage.png">
           </div>
         </div>
       </a>
     </div>
     <!--新增应用管理 end -->
   </div>
   ```

   这个时候在浏览器刷新下页面，点击**左侧栏**的**应用管理**，这个时候地址栏变成了<http://localhost:8080/#cardtable/cardtable>，页面一片空白，到这里，这一步已经完成了

## 3 如何使用 Kero 定义 viewModel, 一起与 UI 的关联

### 3.1 Kero定位

Kero依托基于 MVVM 架构的 Knockout 类库，实现了将NeoUI控件库自由进行数据绑定的前端类库。主要解决问题：

- 提供NeoUI完整样式，解决页面UE风格一致的问题
- 提供了数据模型，实现数据与UI双向绑定，构建数据驱动型页面。解决具有复杂交互的页面开发问题。
- 依托NeoUI控件库，给开发者带来一站式完整前端解决方案

### 3.2 Kero优势

- **兼容IE8以上的主要浏览器**：IE 8+、Firefox、Chrome、safari
- **完善的控件体系**：包含常用控件，见[NeoUI](http://moy.tinper.org/neoui/index.html)，支持多端适配。
- **声明式绑定**：使用简明易读的语法很容易地将模型数据关联到DOM元素上
- **双向数据绑定**：模型与UI之间的双向自动更新
- **多维数据模型**：解决了字段关联、主子数据、主子孙等多维数据模型的绑定问题。

### 3.3 起步引入 Kro 文件以及相关依赖

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Kero Getting Started</title>
</head>
<body>

  <script src="http://design.yonyoucloud.com/static/jquery/jquery-1.9.1.min.js"></script>
  <!--引入knockout依赖-->
  <script src="http://design.yonyoucloud.com/static/knockout/knockout-3.2.0.debug.js"></script>
  <!--引入核心js文件-->
  <script src="http://design.yonyoucloud.com/static/uui/latest/js/u.js"></script>
</body>
</html>
```

### 3.4 兼容 IE8

```
<!--[if lte IE 8]>
  <script src="http://design.yonyoucloud.com/static/uui/latest/js/u-polyfill.js"></script>
<![endif]-->
```

### 3.5 获取 `Kero` 资源

kero资源已打包在`u.js`中，配合`u.css` ， 依赖`jquery`实现完整前端UI方案。

如需使用到grid，tree相关插件，可选择添加对应的`css`和`js`文件，页面结构如下：

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">

  <!-- 整体样式u.css,必须引入 -->
  <link rel="stylesheet" href="//design.yonyoucloud.com/static/uui/latest/css/u.css">

  <!-- 可选：使用grid图表相关插件，加载grid.css -->
  <link rel="stylesheet" type="text/css" href="//design.yonyoucloud.com/static/uui/latest/css/grid.css">

  <!-- 可选：使用tree相关插件，加载tree.css -->
  <link rel="stylesheet" type="text/css" href="//design.yonyoucloud.com/static/uui/latest/css/tree.css">
</head>
<body>
  <h1> Hi, iuap design </h1>

  <!-- 你的代码 -->

  <!-- 依赖jQuery,必须在核心js加载前引入 -->
  <script src="//design.yonyoucloud.com/static/jquery/jquery-1.11.2.js"></script>

  <!--[if lte IE 8 ]>
  <!-- 针对ie8,Polyfill -->
  <script src="//design.yonyoucloud.com/static/uui/latest/js/u-polyfill.js"></script>
  <![endif]-->

  <!-- 核心js 必须引入 -->
  <script src="//design.yonyoucloud.com/static/uui/latest/js/u.js"></script>

  <!-- 可选：使用grid图表相关插件，加载u-grid.js -->
  <script src="//design.yonyoucloud.com/static/uui/latest/js/u-grid.js"></script>

  <!-- 可选：使用tree相关插件，加载u-tree.js -->
  <script src="//design.yonyoucloud.com/static/uui/latest/js/u-tree.js"></script>

</body>
</html>
```

### 3.6 Kero设计理念

#### **UI控件**

UI控件遵循iUAP Design设计规范，构建跨平台和超越设备尺寸的统一体验。遵循基本的移动设计定则，同时支持触摸、语音、鼠标、键盘等输入方式。

UI控件的使用，采用了类似bootstrap的用法，通过定义class名称来声明控件，如按钮控件的定义：

```
<button class="u-button">BUTTON</button>
```

开发者不需要通过js代码创建控件，简单易用，详见[NeoUI](http://moy.tinper.org/neoui/index.html)。

#### **模型结构**

##### 数据模型

数据模型主要是对MVVM架构中的Model层做增强处理。主要功能有：

- 以行、列的形式对数据做存储，并对外暴露一批增删改查的API，方便开发者对页面数据的处理，而且所有开发者之间做到统一，减少出错概率。
- 数据增加状态标识新增或修改，方便开发者使用。
- 具有分页缓存能力，可在前台处理分页(非必要情况下，不推荐前台分页)。
- 具有事件触发器，把数据变化触发出去，供开发者监听使用。

##### 控件模型

控件模型是为解决复杂交互页面中，业务逻辑对数据存在一系列处理需求而设计的。用来简化开发者对相关逻辑的开发。比如：数据的必填、数据的各种校验、数据的显示格式等。

控件模型与UI和数据模型之间的关系表现为：

![img](http://moy.tinper.org/assets/static/img/kero/mvvm.png)

在一般的场景中，数据模型可以直接与UI进行数据绑定。当有数据处理需求时，可以通过控件模型来处理UI和数据模型之间的数据通信。控件模型在处理数据的同时，会进行相关业务逻辑的处理。

## 4 . 数据模型

### 4.1 数据模型(dataTabe)作为MVVM架构中Model层的增强。主要功能有：

- 以行、列的形式，通过json对象对数据做存储，并对外暴露一批增删改查的API，方便开发者对页面数据的处理，而且所有开发者之间做到统一，减少出错概率。
- 数据增加状态标识新增或修改，方便开发者使用。
- 具有分页缓存能力，可在前端处理分页(非必要情况下，不推荐前端分页)。
- 提供事件监听u.on(element, eventName,child,listener)，把数据变化触发出去，供开发者监听使用。

### 4.2  模型定义方法

```
   var myDataTable = new u.DataTable({
        meta:{
            field1:{type:date},
            field2:{}
        }
    })
```

meta中是模型的字段信息，字段名对应的对象为字段的属性定义。其中常用字段的属性定义的有type、以及一些校验属性（详情参考[这里](http://moy.tinper.org/moy/kero-data.html#%E9%AA%8C%E8%AF%81%E8%AE%BE%E7%BD%AEValidate)）、default（设置字段的默认值）以及不同控件的属性设置等。没有字段属性时，可以为空对象。

## 更多 API 请参考[tinper-moyAPI](http://moy.tinper.org/tinper-moy%20%E6%8A%80%E6%9C%AF%20API.html)

##  5 如何调用 Moy 官方组件

### 5.1 调用 UI 组件

- 例子一 按钮组件调用

```
<!--html 增加 带有框架自带 class 样式调用 UI 组件-->
<div class="u-button-group ">
    <button class="u-button">BUTTON</button>
    <button class="u-button">BUTTON</button>
    <button class="u-button">BUTTON</button>
</div>
```

- 例子二 操作组件

```
<!--html 部分 定义 容器/ID /class 样式 根据传入 class 样式不同在页面展现方式也不同 包括 有边框,无边框,有间距等基础样式-->
<div id='pagination' class='u-pagination'>
</div>

```

```
//js 部分代码进行页面数据渲染
var element = document.getElementById("pagination");
var comp = new u.pagination({ el: element,showState:false });
comp.update({ totalPages: 100, pageSize: 20, currentPage: 1, totalCount: 200 });
comp.on('pageChange', function(pageIndex) {
    console.log('新的页号为' + pageIndex);
});
comp.on('sizeChange', function(arg) {
    console.log('每页显示条数为' + arg[0]);
});
```



- 例子三 JavaScript 组件(以表格组件为例)

```
<!--html 创建 div-->
<div class="grid-body">
    <div class="grid" id="grid-comp1"></div>
</div>
```

```
创建 column 对象
var colu = [{
     field: "id",
    title: "id"
}, {
    field: "pid",
    title: "pid"
}, {
    field: "column1",
    title: "column1"
}, {
    field: "column2",
    title: "column2"
}, {
    field: "column3",
    title: "column3"
}
];
```

```
创建数据(理论上数据应该从后台获取)
var data1 = {
    values: [{
        column1: "11",
        column2: "12",
        column3: "13",
        id: '0',
        pid: ''
    }, {
        column1: "21",
        column2: "22",
        column3: "23",
        id: '1',
        pid: '0'
    }, {
        column1: "31",
        column2: "32",
        column3: "33",
        id: '3',
        pid: '1'
    }
    ]
};
```

```
js 部分创建表格控件
$("#grid-comp1").grid({
    dataSource: data1,
    id: 'case-g1',
    editable: true,
    keyField: 'id',
    columnmenu: false,
    parentKeyField: 'pid',
    columns: colu
});
```





