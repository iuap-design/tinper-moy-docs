---
title: 日期时间选择
type: moy
order: 11
---
#### 日期时间选择

本例展示:日期时间UI控件绑定默认数据。

[试一试](http://tinper.org/webide/#/demos/kero/datetime)

注意：

1、`u-datepicker`元素中format用来定义日期的显示格式，具体定义请参考UI控件中的[日期](http://docs.tinper.org/neoui/plugin.html#日期)中的定义



#### API

#### u-meta 属性

* type：`u-date`或者`u-datetime`。默认为`u-date`
	* `u-date`:年-月-日
	* `u-datetime`：年-月-日 时：分：秒


* beforeValueChangeFun
	* 类型： String
	* 说明：用户自定义点击确认按钮触发的事件。其值代表函数名称，此函数在viewModel中定义。其中参数为当前用户选择的时间。

* format
	* 类型：String
	* 说明：日期的显示格式。具体请参考[日期控件](http://docs.tinper.org/neoui/plugin.html#日期)。默认显示"YYYY-MM-DD HH:mm:ss"
* startField
	* 类型：String
	* 说明：日期的起始时间

* endField
	* 类型：String
	* 说明：日期的结束日期


u-meta基础api请参考[这里](http://docs.tinper.org/moy/kero-model.html#Type类型)



#### DateTimeAdapter对象

* 类型：`Object`
* 说明： 获取DateTimeAdapter对象，可以通过此对象的一些方法来改变日期控件的效果状态。下面方法均是在此对象基础上调用的。
* 用法：`app.getComp('控件id值')；`



```

<div class='u-datepicker' u-meta='{"id":"udatetime","type":"u-datetime","data":"dt1","field":"f1","format":"YYYY-MM-DD HH:mm"}'>
    <input class="u-input" type="text">
    <span class="input-group-addon"><span class="glyphicon glyphicon-calendar"></span>
    </span>
</div>


var dateTimeAObject = app.getComp('udatetime');//udatetime为在u-meta中定义的id值

```

#### setEnable对象

* 类型： `Function`
* 说明： 设置日期控件是否可用。
* 参数：{Boolean} isEnable,isEnable=true时可用，isEnable=false时不可用
* 用法：

```
dateTimeAObject.setEnable(true);//设置可用

```



相关内容：

[基础日期控件](http://docs.tinper.org/neoui/plugin.html#日期)    

[日期控件在grid中使用](http://tinper.org/webide/#/demos/grids/edit)


#### Datetime

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
	format:日期控件特有属性。type为u-date时format默认为“YYYY-MM-DD”，type为u-datetime时format默认为“YYYY-MM-DD HH:mm:ss”
-->
<div class='u-datepicker' u-meta='{&quot;id&quot;:&quot;udatetime&quot;,&quot;type&quot;:&quot;u-datetime&quot;,&quot;data&quot;:&quot;dt1&quot;,&quot;field&quot;:&quot;f1&quot;,&quot;format&quot;:&quot;YYYY-MM-DD HH:mm&quot;}'>
    <input class="u-input" type="text">
    <span class="input-group-addon"><span class="glyphicon glyphicon-calendar"></span>
	</span>
</div>
</div>



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
            f1: {type:'datetime'}
        }
    })
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
r.setValue('f1', "2016-2-13 4:58:58");
viewModel.dt1.setRowSelect(0);



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
	format:日期控件特有属性。type为u-date时format默认为“YYYY-MM-DD”，type为u-datetime时format默认为“YYYY-MM-DD HH:mm:ss”
-->
<div class='u-datepicker' u-meta='{"id":"udatetime","type":"u-datetime","data":"dt1","field":"f1","format":"YYYY-MM-DD HH:mm"}'>
    <input class="u-input" type="text">
    <span class="input-group-addon"><span class="glyphicon glyphicon-calendar"></span>
	</span>
</div>

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
            f1: {type:'datetime'}
        }
    })
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
r.setValue('f1', "2016-2-13 4:58:58");
viewModel.dt1.setRowSelect(0);



```

