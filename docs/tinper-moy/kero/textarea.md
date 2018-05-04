---
title: 多行文本输入控件
type: moy
order: 23
---
#### 多行文本输入控件

本例展示kero与多行文本输入控件textarea结合示例。

[试一试](http://tinper.org/webide/#/demos/kero/textarea)


#### API

#### u-meta 属性

* type：`textarea`



本例实现如下效果：

{% raw %}
<div class="example-content"><!--
	HTML
	u-meta:框架特有标记，框架通过识别此标记创建对应UI组件，以及进行数据绑定
	id,type.data,field为必选项
	id:创建组件唯一标识
	type:创建组件对应的类型
	data:指定数据模型中的数据集
	field:绑定数据集中对应的字段
-->
<div id="txtWrap">
    <textarea u-meta='{&quot;id&quot;:&quot;textareaAdapter&quot;,&quot;data&quot;:&quot;dt1&quot;,&quot;field&quot;:&quot;f1&quot;,&quot;type&quot;:&quot;textarea&quot;}'></textarea>
</div>
</div>

<style>
#txtWrap textarea{
	width: 80%;
	margin-left: 10px;
	padding: 20px;
}

</style>

<script>
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 */
 var app, viewModel;
 viewModel = {
     dt1: new u.DataTable({
         meta: {
             f1: {}
         }
     }),
 }

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el: 'body',
    model: viewModel
});

// 数据集dt1创建空行，并为字符f1赋值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "落红不是无情物，化作春泥更护花.－龚自珍《己亥杂诗》 ");

</script>

{% endraw %}
``` html
<!--
	HTML
	u-meta:框架特有标记，框架通过识别此标记创建对应UI组件，以及进行数据绑定
	id,type.data,field为必选项
	id:创建组件唯一标识
	type:创建组件对应的类型
	data:指定数据模型中的数据集
	field:绑定数据集中对应的字段
-->
<div id="txtWrap">
    <textarea u-meta='{"id":"textareaAdapter","data":"dt1","field":"f1","type":"textarea"}'></textarea>
</div>

```
``` css
#txtWrap textarea{
	width: 80%;
	margin-left: 10px;
	padding: 20px;
}

```
``` js
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 */
 var app, viewModel;
 viewModel = {
     dt1: new u.DataTable({
         meta: {
             f1: {}
         }
     }),
 }

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el: 'body',
    model: viewModel
});

// 数据集dt1创建空行，并为字符f1赋值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "落红不是无情物，化作春泥更护花.－龚自珍《己亥杂诗》 ");

```

