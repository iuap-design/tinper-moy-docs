# tinper-moy 概述
## 1.  企业级应用开发中遇到的问题及解决方案?

### 1.1 开发中的痛点

- 开发者技术水平不一了解知识面也不尽相同
- 需要掌握诸多技术 如: JS CSS 等
- 时间短快速开发项目并且交付项目
- 数据处理逻辑较为复杂/复杂单据
- 页面呈现调试困难
- 控件复杂,不断扩展
- 数据格式不固定,运行时动态调整

### 1.2 如何解决开发中的痛点

- 提供一套易掌握并好上手的技术框架
- 框架提供完整的组件减少开发者对 JS/CSS 的编写
- 框架易用性
- 框架提供较全的数据处理方案
- 基于框架封装的平台快速开发
- 数据模型可描述

## 2. Moy 是什么?

### 2.1moy 组成

- 2.1.1工程化 gulp less sass webpack commonJS ES6 
- 2.1.2.路由 Router director.js
- 2.1.3.AMD  模块化 引入需要的文件 js css 等文件
- 2.1.4.数据模型 mvvm
- 2.1.5.页面和数据如何连接到一起：u-meta
- 2.1.6页面元素 UI框架neoui。 [neoui](http://docs.tinper.org/neoui/)


- 2.1.7数据 kero数据模型。[kero](http://docs.tinper.org/moy/kero-api.html#)
- 2.1.8复杂表格。[grid](http://docs.tinper.org/moy/grid_index.html)
- 2.1.9树表。[tree](http://docs.tinper.org/moy/kero/tree.html)
- 2.1.10如何快速预览和拷贝和调试？[在线调试例子](http://tinper.org/webide/#/demos/ui/button)

### 2.2 Moy 技术依赖拓扑图

- 2.2.1![效果](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/概述/kuangjia.png)

### 2.3 Moy 实现效果展示

- 2.3.1![效果](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/概述/xiaoguo.gif)

## 3. Moy 的特点和能力

### 3.1 数据模型可描述

- 描述性的代码风格定义数据模型。数据被存储在ViewModel中,通过数据模型进行访问和修改。

```
var viewModel = {
    head : new u.DataTable({
        meta: {
            'pk_org': {
                'required': true,
                'associations': {
                    "pk_org": "name"
                },
                'associationMeta': 'uap.org'
            },
            'billnumber': {
                'precision': 2,
                'required': true,
                'maxLength': 50
            }
        }
    })
}
```

### 3.2 统一可扩展的控件描述 

- 使用了描述性的风格来定义控件

```
<input type="text" u-meta='{"type":"string", "data":"head", "field":"billnumber"}' />
```

在普通 HTML 中使用kero语法将在指定DOM上创建控件,并与数据模型关联。一旦创建了关联，控件 将与数据模型同步。每当修改了数据，控件便相应地更新,修改了控件,数据模型也会相应的更新.

扩展控件时可以通过数据模型对数据进行获取&监听和修改

### 3.3 数据模型可变

- 数据格式可变使得无缝的数据修改称为可能， kero负责把不同控件的数据集中高效地组织并处理，视图层的控件会订阅数据模型及数据的变更，当数据变化时通知相应组件更新，并在客户端维护一份包含所有数据的数据缓存

## 4.Moy数据模型定位

###  4.1 数据模型能力

依托基于 [MVVM](http://tinper.org/dist/kero/docs/mvvm.html) 架构的 [Knockout](http://tinper.org/dist/kero/docs/knockout.html) 类库，实现了将NeoUI控件库自由进行数据绑定的前端类库。主要解决问题：

- 提供NeoUI完整样式，解决页面UE风格一致的问题
- 提供了数据模型，实现数据与UI双向绑定，构建数据驱动型页面。解决具有复杂交互的页面开发问题。
- 依托NeoUI控件库，给开发者带来一站式完整前端解决方案

##  5.Moy 优势

### 5.1 优势

- **兼容IE8以上的主要浏览器**：IE 8+、Firefox、Chrome、safari
- **完善的控件体系**：包含常用控件，见[NeoUI](http://tinper.org/dist/kero/neoui/index.html)，支持多端适配。
- **声明式绑定**：使用简明易读的语法很容易地将模型数据关联到DOM元素上
- **双向数据绑定**：模型与UI之间的双向自动更新
- **多维数据模型**：解决了字段关联、主子数据、主子孙等多维数据模型的绑定问题。

## 6.设计理念

### 6.1 UI控件

UI控件遵循iUAP Design设计规范，构建跨平台和超越设备尺寸的统一体验。遵循基本的移动设计定则，同时支持触摸、语音、鼠标、键盘等输入方式。

UI控件的使用，采用了类似bootstrap的用法，通过定义class名称来声明控件，如按钮控件的定义：

```
<button class="u-button">BUTTON</button>
```

开发者不需要通过js代码创建控件，简单易用，详见[NeoUI](http://tinper.org/dist/kero/neoui/index.html)。

### 6.2 模型结构

#### 数据模型

数据模型主要是对MVVM架构中的Model层做增强处理。主要功能有：

- 以行、列的形式对数据做存储，并对外暴露一批增删改查的API，方便开发者对页面数据的处理，而且所有开发者之间做到统一，减少出错概率。
- 数据增加状态标识新增或修改，方便开发者使用。
- 具有分页缓存能力，可在前台处理分页(非必要情况下，不推荐前台分页)。
- 具有事件触发器，把数据变化触发出去，供开发者监听使用。

#### 控件模型

控件模型是为解决复杂交互页面中，业务逻辑对数据存在一系列处理需求而设计的。用来简化开发者对相关逻辑的开发。比如：数据的必填、数据的各种校验、数据的显示格式等。

## 7.如何参与 Moy 的开源工作?

### 7.1 框架所有仓库结构图

![框架所有仓库结构说明](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/%E6%A6%82%E8%BF%B0/%E6%A1%86%E6%9E%B6%E6%89%80%E6%9C%89%E4%BB%93%E5%BA%93%E7%BB%93%E6%9E%84%E8%AF%B4%E6%98%8E.png)

### 7.2 框架核心仓库结构图

![框架核心仓库结构说明](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/%E6%A6%82%E8%BF%B0/%E6%A1%86%E6%9E%B6%E6%A0%B8%E5%BF%83%E4%BB%93%E5%BA%93%E7%BB%93%E6%9E%84%E8%AF%B4%E6%98%8E.png)

以下针对结构图进行分层说明：

### 7.3 框架基础

- tinper-sparrow：提供框架基础api
- compox：框架创建组件的核心逻辑，主要包括compMgr以及createApp
- tinper-neoui：基于compox规范定义各个UI组件
- compox-util：app所提供的工具api，方便功能开发人员进行操作

### 7.4 数据层

- kero：做为MVVM架构中Model层的增强，提供多维数据模型
- kero-fetch：主要提供与服务器交互时所需的方法，需和后台数据模型联合使用

### 7.5 适配层

- neoui-kero：针对各个组件进行适配
- neoui-kero-mixin：对neoui-keo适配层的公共逻辑进行提取，neoui-kero中可根据需要添加对应的mixin
- jquery插件/IE8兼容
- tinper-neoui-grid：基于jquery实现的grid组件
- tinper-neoui-tree：第三方tree插件 ztree
- tinper-neoui-polyfill：IE8兼容处理

### 7.6 原理

所有的js对象都继承自class

new对象时都会调用initialize方法，UI组件基类BaseComponent与u-meta组件基类BaseAdapter的initialize方法中都会调用init方法，因此各个组件需要将init作为入口方法并进行实现

UI组件注册

- CompMgr.regComp：注册UI组件，将comp与css进行关联
- UI组件解析过程
- CompMgr.updateComp：针对页面的css进行解析，生成UI组件

### 7.7 u-meta组件

- CompMgr.addDataAdapter：注册适配层，将compAdapter于type进行关联
- u-meta组件解析过程

![u-meta组件解析过程](http://iuap-design-cdn.oss-cn-beijing.aliyuncs.com/static/moy/images/%E6%A6%82%E8%BF%B0/u-meta%E7%BB%84%E4%BB%B6%E8%A7%A3%E6%9E%90%E8%BF%87%E7%A8%8B.png)

- createApp：针对页面的u-meta进行解析，生成组件并与datatable进行绑定
- app.init：针对页面的u-meta进行解析的核心方法，遍历所有的u-meta元素调用compMgr.createDataAdapter生成每个组件
- compMgr.createDataAdapter：针对传入的type级u-meta属性new对应的adapter

### 7.8 mixin说明

neoui-kero-mixin仓库对neoui-kero适配层的公共逻辑进行提取

- BaseAdapter中默认添加了ValueMixin,EnableMixin, RequiredMixin, ValidateMixin，如果新增组件有特殊需求可通过自定义mixins属性来调整添加的mixin
- BaseAdapter中的initialize方法会将mixin中的methods添加至当前组件，并且在方法最后会调用mixin的init方法进行初始化

### 7.9 ValueMixin

处理数据在tinper-neoui与kero之间的交互操作。以下对核心API进行说明：

- modelValueChange：数据模型改变时执行的方法，可针对实际情况在各组件中重写
- setShowValue：modelValueChange中对数据格式化之后调用此方法修改UI层的战士，可针对实际情况在各组件中重写
- setValue：UI层改变时执行的方法，提供接口beforeSetValue并在setValue最开始调用，可针对实际情况在各组件中重写beforeSetValue以便对数据进行格式化等操作

### 7.10 EnableMixin

根据u-meta中的enable属性传入UI层，并监听datatable的Enable属性变化。以下对核心API进行说明：

- setEnable：设置UI层的enable展示，可针对实际情况在各组件中重写

RequiredMixin

根据u-meta中的required属性传入UI层，并监听datatable的required属性变化。以下对核心API进行说明：

- setRequired：设置UI层的必输展示，可针对实际情况在各组件中重写

ValidateMixin

根据datatable或u-meta中的校验属性定义来生成校验组件，并没有监听datatable中的属性变化，后续考虑优化。以下对核心API进行说明：

- doValidate：调用当前组件的数据校验