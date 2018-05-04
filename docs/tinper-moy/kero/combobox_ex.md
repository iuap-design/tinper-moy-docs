---
title: 下拉框
type: moy
order: 8
---
#### 下拉框

本例展示下拉框示例。

[试一试](http://tinper.org/webide/#/demos/kero/combobox)


#### API

#### u-meta 属性

* type：`u-combobox`

* datasource
	* 类型： Array
	* 说明：设置下拉框的数据源，具体数组内容需要在viewmodel中定义，数组中的每个对象需要有value，name字段。其中name为下拉框的显示值，value为下拉框的真实值。
	* 用法：

		```

		comboData:[{name:'cc',value:'03'},{name:'dd',value:'04'}]

		```

**注**：如果在开发时要求兼容ie8,ie9，datasource必须定义。　


u-meta基础api请参考[这里](http://docs.tinper.org/moy/kero-model.html#Type类型)



#### ComboboxAdapter对象

* 类型：`Object`
* 说明： 获取ComboboxAdapter对象，可以通过此对象的一些方法来改变下拉框的效果状态。下面方法均是在此对象基础上调用的。
* 用法：`app.getComp('控件id值')；`



```

<div id="combo1" class="u-combo u-text u-label-floating" u-meta='{"id":"c1","type":"u-combobox","data":"dt1","field":"f1","datasource":"comboData"}'>
    <input class="u-input"/>
    <span class="u-combo-icon"></span>
</div>

var comboboxAObject = app.getComp('c1');//c1为在u-meta中定义的id值

```


#### setEnable对象

* 类型： `Function`
* 说明： 设置下拉框是否可用。
* 参数：{Boolean} isEnable,isEnable=true时可用，isEnable=false时不可用
* 用法：

```
comboboxAObject.setEnable(true);//设置可用

```


相关内容：

[基础下拉框](http://docs.tinper.org/neoui/plugin.html#下拉框)    

[下拉框在grid中使用](http://tinper.org/webide/#/demos/grids/edit)


#### Combobox

本例实现如下效果：

* 实现下拉菜单效果
* 实现JS更改下拉菜单默认数据`setComboData(arg)`

{% raw %}
<div class="example-content"><!-- 
	HTML
	u-meta:框架特有标记，框架通过识别此标记创建对应UI组件，以及进行数据绑定 
	id,type.data,field为必选项
	id:创建组件唯一标识
	type:创建组件对应的类型
	data:指定数据模型中的数据集
	field:绑定数据集中对应的字段
	datasource:绑定数据模型对应的数据
-->
<div id="combo1" class="u-combo u-text u-label-floating" u-meta='{&quot;id&quot;:&quot;dt1&quot;,&quot;type&quot;:&quot;u-combobox&quot;,&quot;data&quot;:&quot;dt1&quot;,&quot;field&quot;:&quot;f1&quot;,&quot;datasource&quot;:&quot;comboData&quot;}'>
    <input class="u-input"/>
    <span class="u-combo-icon"></span>
</div></div>



<script>
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 * comboData:指定默认的下拉数据集
 */
var app, viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta: {
            f1: {},
            f2: {}
        }
    }),
    comboData:[{name:'cc',value:'03'},{name:'dd',value:'04'}]
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


/**
 * 修改viewModel默认绑定的数据值
 * @type {Array}
 */
var combo1Data = [{name:'cc1',value:'03'},{name:'dd1',value:'04'}];
var combo1Obj = document.getElementById('combo1')['u.Combo'];

combo1Obj.setComboData(combo1Data);

// 创建空行，设置默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "test1");
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
	datasource:绑定数据模型对应的数据
-->
<div id="combo1" class="u-combo u-text u-label-floating" u-meta='{"id":"dt1","type":"u-combobox","data":"dt1","field":"f1","datasource":"comboData"}'>
    <input class="u-input"/>
    <span class="u-combo-icon"></span>
</div>
```

``` js
// JS

/**
 * viewModel 创建数据模型
 * dt1 创建的数据集
 * f1 创建数据集中的字段
 * type:指定数据对应的类型
 * comboData:指定默认的下拉数据集
 */
var app, viewModel;
viewModel = {
    dt1: new u.DataTable({
        meta: {
            f1: {},
            f2: {}
        }
    }),
    comboData:[{name:'cc',value:'03'},{name:'dd',value:'04'}]
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


/**
 * 修改viewModel默认绑定的数据值
 * @type {Array}
 */
var combo1Data = [{name:'cc1',value:'03'},{name:'dd1',value:'04'}];
var combo1Obj = document.getElementById('combo1')['u.Combo'];

combo1Obj.setComboData(combo1Data);

// 创建空行，设置默认值
var r = viewModel.dt1.createEmptyRow();
r.setValue('f1', "test1");
viewModel.dt1.setRowSelect(0);


```

