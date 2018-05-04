---
title: 分页
type: moy
order: 14
---
#### 分页

本例实现NeoUI组件pagination数据绑定。


#### Pagination

本例实现如下效果：

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
	datasource:绑定数据
-->
	<div id='pagination' class='u-pagination'  u-meta='{&quot;type&quot;:&quot;pagination&quot;,&quot;data&quot;:&quot;listData&quot;}'>
    </div>
</div>



<script>
// JS

/**
 * viewModel 创建数据模型
 * listData 创建的数据集
 * enterprise、depart、name、sex 创建数据集中的字段
 * type:指定数据对应的类型
 */
var app;
var viewModel = {
    listData: new u.DataTable({
        meta: {
            enterprise: {type: 'string'},
            depart: {type: 'string'},
            name: {type: 'string'},
            sex: {type: 'string'}
        }
    })
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app=u.createApp({
    el:'body',
    model:viewModel
});

//dataTable设置值
viewModel.listData.setSimpleData([
    {"enterprise": "用友","depart": "UE","name": "张紫琼","sex": "male"},
    {"enterprise": "阿里巴巴","depart": "测试","name": "张丽丹","sex": "female"}
]);

viewModel.listData.totalPages(10);

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
	datasource:绑定数据
-->
	<div id='pagination' class='u-pagination'  u-meta='{"type":"pagination","data":"listData"}'>
    </div>

```

``` js
// JS

/**
 * viewModel 创建数据模型
 * listData 创建的数据集
 * enterprise、depart、name、sex 创建数据集中的字段
 * type:指定数据对应的类型
 */
var app;
var viewModel = {
    listData: new u.DataTable({
        meta: {
            enterprise: {type: 'string'},
            depart: {type: 'string'},
            name: {type: 'string'},
            sex: {type: 'string'}
        }
    })
};

/**
 * app 创建框架服务
 * el 指定服务对应的顶层DOM
 * model 指定服务对应的数据模型
 */
app=u.createApp({
    el:'body',
    model:viewModel
});

//dataTable设置值
viewModel.listData.setSimpleData([
    {"enterprise": "用友","depart": "UE","name": "张紫琼","sex": "male"},
    {"enterprise": "阿里巴巴","depart": "测试","name": "张丽丹","sex": "female"}
]);

viewModel.listData.totalPages(10);

```

