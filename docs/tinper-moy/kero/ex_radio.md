---
title: 单选框
type: moy
order: 17
---
#### 单选框

本例实现NeoUI组件radio的数据绑定。

[试一试](http://tinper.org/webide/#/demos/kero/radio)

**注意**：

1、datasource对应的对象需要在数据模型viewModel中定义。

2、radio选中的真实值会绑定到dataTable对应的字段上


#### API

#### u-meta 属性

* type：`u-radio`

* datasource
	* 类型： Array
	* 说明：设置单选框的数据源，具体数组内容需要在viewmodel中定义，数组中的每个对象需要有value，name字段。其中name为单选框的显示值，value为单选框的真实值。
	* 用法：

		```

		radiodata:[{value:'01',name:'男'},{value:'02',name:'女'}]

		```
* hasOther
	* 类型：Boolean
	* 说明：是否含有其他单选框，当hasOther为true时，单选框会自动多一个显示值为“其他”的单选框和一个输入框，输入框默认是不可输入的，当单选框选中时，输入框可输入，存放该单选框的真实值。默认为false。


#### radioAdapter对象

* 类型：`Object`
* 说明： 获取radioAdapter对象，可以通过此对象的一些方法来改变单选框的效果状态。下面方法均是在此对象基础上调用的。
* 用法：`app.getComp('控件id值')；`



```

<div u-meta='{"id":"r1","type":"u-radio","data":"dt1","field":"f1","datasource":"radiodata","hasOther":true}'>
	<label  class="u-radio" >
	    <input type="radio" class="u-radio-button" name="options">
	    <span class="u-radio-label"></span>
	</label>
</div>

var radioAObject = app.getComp('r1');//r1为在u-meta中定义的id值

```


#### setEnable对象

* 类型： `Function`
* 说明： 设置单选框是否可用。
* 参数：{Boolean} isEnable,isEnable=true时可用，isEnable=false时不可用
* 用法：

```
radioAObject.setEnable(true);//设置可用

```



相关内容：

[基础单选框](http://docs.tinper.org/neoui/plugin.html#单选框)  

[单选框在grid中使用](http://tinper.org/webide/#/demos/grids/edit)


实现效果如下：
{% raw %}
<div class="example-content"><!-- 
	HTML
	u-meta:框架特有标记，框架通过识别此标记创建对应UI组件，以及进行数据绑定 
	id,type.data,field为必选项
	id:创建组件唯一标识
	type:创建组件对应的类型,单选框对应的type为u-radio
	data:指定数据模型中的数据集
	field:绑定数据集中对应的字段
	datasource:绑定数据
-->
<div u-meta='{&quot;id&quot;:&quot;r1&quot;,&quot;type&quot;:&quot;u-radio&quot;,&quot;data&quot;:&quot;dt1&quot;,&quot;field&quot;:&quot;f1&quot;,&quot;datasource&quot;:&quot;radiodata&quot;}'>
    <label  class="u-radio" >
        <input type="radio" class="u-radio-button" name="options">
        <span class="u-radio-label"></span>
    </label>
</div></div>



<script>

// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 * radiodata:自定义单选框数据，用于绑定数据
 */
var app,viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta:{
        f1:{},
        f2:{}
        }
     }),
    radiodata:[{value:'01',name:'男'},{value:'02',name:'女'}]
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el:'body',
    model:viewModel
});

// 创建空行,绑定默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1',"01");
viewModel.dt1.setRowSelect(0);
</script>

{% endraw %}
``` html
<!-- 
	HTML
	u-meta:框架特有标记，框架通过识别此标记创建对应UI组件，以及进行数据绑定 
	id,type.data,field为必选项
	id:创建组件唯一标识
	type:创建组件对应的类型,单选框对应的type为u-radio
	data:指定数据模型中的数据集
	field:绑定数据集中对应的字段
	datasource:绑定数据
-->
<div u-meta='{"id":"r1","type":"u-radio","data":"dt1","field":"f1","datasource":"radiodata"}'>
    <label  class="u-radio" >
        <input type="radio" class="u-radio-button" name="options">
        <span class="u-radio-label"></span>
    </label>
</div>
```

``` js

// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 * radiodata:自定义单选框数据，用于绑定数据
 */
var app,viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta:{
        f1:{},
        f2:{}
        }
     }),
    radiodata:[{value:'01',name:'男'},{value:'02',name:'女'}]
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app = u.createApp({
    el:'body',
    model:viewModel
});

// 创建空行,绑定默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1',"01");
viewModel.dt1.setRowSelect(0);
```

