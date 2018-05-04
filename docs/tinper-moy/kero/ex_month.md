---
title: 月份选择
type: moy
order: 12
---
#### 月份选择

本例展示:月份UI控件绑定默认数据。

[试一试](http://tinper.org/webide/#/demos/kero/month)


**注**：设置月份时，通过dataTable中的对应行row调用setValue设置字段值即可。eg：`row.setValue("f1", "11")`


#### API

#### u-meta 属性

* type：`u-month`

u-meta基础api请参考[这里](http://docs.tinper.org/moy/kero-model.html#Type类型)


相关内容：

[基础月份控件](http://docs.tinper.org/neoui/plugin.html#月份)    

[月份控件在grid中使用](http://tinper.org/webide/#/demos/grids/edit)


#### Month

本例实现如下效果：

* 绑定默认数据
* 实现UI交互

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
<div class="" u-meta='{&quot;id&quot;:&quot;umonth&quot;,&quot;type&quot;:&quot;u-month&quot;,&quot;data&quot;:&quot;dt1&quot;,&quot;field&quot;:&quot;f1&quot;}'>
    <input class="u-input"/>
</div>
</div>



<script>
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 */
var app, viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta: {
            f1: {}
        }
    }),
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el: 'body',
    model: viewModel
});

// 创建空行,绑定默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "11");



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
<div class="" u-meta='{"id":"umonth","type":"u-month","data":"dt1","field":"f1"}'>
    <input class="u-input"/>
</div>

```

``` js
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 */
var app, viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta: {
            f1: {}
        }
    }),
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el: 'body',
    model: viewModel
});

// 创建空行,绑定默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "11");



```

