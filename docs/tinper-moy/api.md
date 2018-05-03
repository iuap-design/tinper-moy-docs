# tinper-moyAPI
## kreo API

<a name="DataTable"></a>

### DataTable : <code>object</code>
前端数据模型对象


* [DataTable](#DataTable) : <code>object</code>
    * _instance_
        * [.id](#DataTable+id) : <code>string</code>
        * [.strict](#DataTable+strict) : <code>boolean</code>
        * [.meta](#DataTable+meta) : <code>object</code>
        * [.enable](#DataTable+enable) : <code>boolean</code>
        * [.pageSize](#DataTable+pageSize) : <code>number</code>
        * [.pageIndex](#DataTable+pageIndex) : <code>number</code>
        * [.totalPages](#DataTable+totalPages) : <code>number</code>
        * [.pageCache](#DataTable+pageCache) : <code>boolean</code>
        * [.params](#DataTable+params) : <code>object</code>
        * [.master](#DataTable+master) : <code>string</code>
        * [.dateNoConvert](#DataTable+dateNoConvert) : <code>boolean</code>
    * _static_
        * [.copyRow(index, row)](#DataTable.copyRow)
        * [.copyRows(index, rows)](#DataTable.copyRows)
        * [.setData(data, options)](#DataTable.setData)
        * [.setValue(fieldName, value, [row], [ctx])](#DataTable.setValue)
        * [.isEnable([fieldName])](#DataTable.isEnable) ⇒ <code>boolean</code>
        * [.setEnable(enable)](#DataTable.setEnable)
        * [.getCurrentRow()](#DataTable.getCurrentRow) ⇒ <code>null</code> &#124; <code>u.Row</code>
        * [.getCurrentIndex()](#DataTable.getCurrentIndex) ⇒ <code>number</code>
        * [.getData()](#DataTable.getData) ⇒ <code>array</code>
        * [.getDataByRule(rule)](#DataTable.getDataByRule) ⇒ <code>array</code>
        * [.getRow(index)](#DataTable.getRow) ⇒ <code>object</code>
        * [.getRowByRowId(rowid)](#DataTable.getRowByRowId) ⇒ <code>Row</code>
        * [.getRowIndex(需要获取索引的row对象)](#DataTable.getRowIndex) ⇒ <code>\*</code>
        * [.getRowsByField(field, value)](#DataTable.getRowsByField) ⇒ <code>array</code>
        * [.getRowByField(field, value)](#DataTable.getRowByField) ⇒ <code>u.Row</code>
        * [.getAllRows()](#DataTable.getAllRows) ⇒ <code>array</code>
        * [.getAllPageRows()](#DataTable.getAllPageRows) ⇒ <code>array</code>
        * [.getChangedDatas(withEmptyRow)](#DataTable.getChangedDatas) ⇒ <code>array</code>
        * [.getChangedRows()](#DataTable.getChangedRows) ⇒ <code>array</code>
        * [.getValue(fieldName, [row])](#DataTable.getValue) ⇒ <code>string</code>
        * [.getIndexByRowId(rowId)](#DataTable.getIndexByRowId)
        * [.getAllDatas()](#DataTable.getAllDatas) ⇒ <code>array</code>
        * [.getRowIdsByIndices(indices)](#DataTable.getRowIdsByIndices) ⇒ <code>array</code>
        * [.getFocusRow()](#DataTable.getFocusRow) ⇒ <code>u.Row</code>
        * [.getFocusIndex()](#DataTable.getFocusIndex) ⇒ <code>number</code>
        * [.getMeta([fieldName], [key])](#DataTable.getMeta) ⇒ <code>object</code>
        * [.getRowMeta([fieldName], [key])](#DataTable.getRowMeta) ⇒ <code>object</code>
        * [.getParam(key)](#DataTable.getParam) ⇒ <code>\*</code>
        * [.getSelectedIndex()](#DataTable.getSelectedIndex) ⇒ <code>number</code>
        * [.getSelectedIndices()](#DataTable.getSelectedIndices) ⇒ <code>array</code>
        * [.getSelectedDatas([withEmptyRow])](#DataTable.getSelectedDatas) ⇒ <code>array</code>
        * [.getSelectedRows()](#DataTable.getSelectedRows) ⇒ <code>array</code>
        * [.getSimpleData([options])](#DataTable.getSimpleData) ⇒ <code>array</code>
        * [.setMeta(fieldName, key, value)](#DataTable.setMeta)
        * [.updateMeta(meta)](#DataTable.updateMeta)
        * [.addParam(key, value)](#DataTable.addParam)
        * [.addParams(params)](#DataTable.addParams)
        * [.refSelectedRows(fieldName)](#DataTable.refSelectedRows)
        * [.ref(fieldName)](#DataTable.ref)
        * [.refMeta(fieldName, key)](#DataTable.refMeta)
        * [.refRowMeta(fieldName, key)](#DataTable.refRowMeta)
        * [.refEnable(fieldName)](#DataTable.refEnable)
        * [.removeRowByRowId(rowId)](#DataTable.removeRowByRowId)
        * [.removeRow(index)](#DataTable.removeRow)
        * [.removeAllRows()](#DataTable.removeAllRows)
        * [.removeRows(indices)](#DataTable.removeRows)
        * [.clear()](#DataTable.clear)
        * [.addRow(row)](#DataTable.addRow)
        * [.addRows(rows)](#DataTable.addRows)
        * [.insertRow(index, row)](#DataTable.insertRow)
        * [.insertRows(index, rows)](#DataTable.insertRows)
        * [.createEmptyRow()](#DataTable.createEmptyRow) ⇒ <code>u.Row</code>
        * [.setAllRowsSelect()](#DataTable.setAllRowsSelect)
        * [.setRowSelect(index)](#DataTable.setRowSelect)
        * [.setRowsSelect(indices)](#DataTable.setRowsSelect)
        * [.addRowSelect(index)](#DataTable.addRowSelect)
        * [.addRowsSelect(indices)](#DataTable.addRowsSelect)
        * [.setAllRowsUnSelect([options])](#DataTable.setAllRowsUnSelect)
        * [.setRowUnSelect(index)](#DataTable.setRowUnSelect)
        * [.setRowsUnSelect(indices)](#DataTable.setRowsUnSelect)
        * [.toggleAllSelect()](#DataTable.toggleAllSelect)
        * [.setRowFocus(index, [quiet], [force])](#DataTable.setRowFocus)
        * [.setRowUnFocus()](#DataTable.setRowUnFocus)
        * [.setSimpleData(data, [options])](#DataTable.setSimpleData)
        * [.addSimpleData(data, status)](#DataTable.addSimpleData)
        * [.on(name, [callback], [one])](#DataTable.on) ⇒ <code>[DataTable](#DataTable)</code>
        * [.off(name, [callback])](#DataTable.off) ⇒ <code>[DataTable](#DataTable)</code>
        * [.one(name, [callback])](#DataTable.one)
        * [.trigger(name)](#DataTable.trigger) ⇒ <code>[DataTable](#DataTable)</code>

<a name="DataTable+id"></a>

#### dataTable.id : <code>string</code>
DataTable对应的唯一标识

<a name="DataTable+strict"></a>

#### dataTable.strict : <code>boolean</code>
在设置数据时是否自动创建对应字段，如果为true则不自动创建，如果为false则自动创建缺失的字段

**Default**: <code>false</code>  
<a name="DataTable+meta"></a>

#### dataTable.meta : <code>object</code>
DataTable的所有字段属性信息

<a name="DataTable+enable"></a>

#### dataTable.enable : <code>boolean</code>
DataTable的是否支持编辑功能

**Default**: <code>true</code>  
<a name="DataTable+pageSize"></a>

#### dataTable.pageSize : <code>number</code>
DataTable支持翻页功能时每页显示数据条数

**Default**: <code>20</code>  
<a name="DataTable+pageIndex"></a>

#### dataTable.pageIndex : <code>number</code>
DataTable支持翻页功能时当前页码

**Default**: <code>0</code>  
<a name="DataTable+totalPages"></a>

#### dataTable.totalPages : <code>number</code>
DataTable支持翻页功能时总页数

**Default**: <code>0</code>  
<a name="DataTable+pageCache"></a>

#### dataTable.pageCache : <code>boolean</code>
DataTable的是否支持前端缓存，支持前端缓存则前端会存储所有页的数据信息，否则只保存当前页的数据信息。如果使用前端缓存则需要使用框架封装的fire方法来与后台进行交互

**Default**: <code>false</code>  
<a name="DataTable+params"></a>

#### dataTable.params : <code>object</code>
使用者自定义的属性合集，框架内部不会针对此属性进行特殊处理，仅用于设置及获取

<a name="DataTable+master"></a>

#### dataTable.master : <code>string</code>
使用者自定义的属性，框架内部不会针对此属性进行特殊处理，仅用于设置及获取。

<a name="DataTable+dateNoConvert"></a>

#### dataTable.dateNoConvert : <code>boolean</code>
通过getSimpleData获取数据时，日期字段是否转化为long型，如果为true时不进行转化，为false时转化为long型

**Default**: <code>false</code>  
<a name="DataTable.copyRow"></a>

#### DataTable.copyRow(index, row)
在指定index位置插入单条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 数据行插入之后的位置 |
| row | <code>object</code> | 数据行信息 |

**Example**  
```js
var row = {
   field1:'value1'
}
datatable.copyRow(1,row)
```
<a name="DataTable.copyRows"></a>

#### DataTable.copyRows(index, rows)
在指定index位置插入多条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 数据行插入之后的位置 |
| rows | <code>array</code> | 存储数据行信息的数组 |

**Example**  
```js
var row1 = {
   field1:'value1'
}
var row2 = {
   field1:'value1'
}
datatable.copyRow(1,[row1,row2])
```
<a name="DataTable.setData"></a>

#### DataTable.setData(data, options)
设置数据信息


| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| data | <code>object</code> |  | 需要设置的数据信息，必须包含rows或者pages属性 |
| [data.rows] | <code>array</code> |  | 数据信息中的行信息数组 |
| [data.pages] | <code>array</code> |  | 数据信息中的page对象数组 |
| [data.pageIndex] | <code>number</code> | <code>DataTable对象当前的页码</code> | 数据信息中的当前页码 |
| [data.pageSize] | <code>number</code> | <code>DataTable对象当前的每页显示条数</code> | 数据信息中的每页显示条数 |
| [data.totalPages] | <code>number</code> | <code>DataTable对象当前的总页数</code> | 数据信息中的总页数 |
| [data.totalRow] | <code>number</code> | <code>如果存在rows则为rows的长度，否则为DataTable对象当前的总条数</code> | 数据信息中的总条数 |
| [data.select] | <code>number</code> |  | 数据信息中的选中行行号 |
| [data.focus] | <code>number</code> |  | 数据信息中的focus行行号 |
| options | <code>object</code> |  | 设置数据时的配置参数 |
| options.unSelect | <code>boolean</code> | <code>false</code> | 是否默认选中第一行，如果为true则不选中第一行，否则选中第一行 |

**Example**  
```js
var data = {
   rows:[{
     filed1:'value1',
     field2:'value2'
   },{
     filed1:'value11',
     field2:'value21'
   }],
   select:0,
}
var op = {
    unSelect:true
}
datatable.setData(data,op)
```
<a name="DataTable.setValue"></a>

#### DataTable.setValue(fieldName, value, [row], [ctx])
设置对应行对应字段的值


| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| fieldName | <code>string</code> |  | 需要设置的字段 |
| value | <code>string</code> |  | 需要设置的值 |
| [row] | <code>u.row</code> | <code>当前行</code> | 需要设置的u.row对象， |
| [ctx] | <code>\*</code> |  | 自定义属性，在valuechange监听传入对象中可通过ctx获取此处设置 |

**Example**  
```js
datatable.setValue('filed1','value1') //设置当前行字段值
var row = datatable.getRow(1)
datatable.setValue('filed1','value1',row) //设置在指定行字段值
datatable.setValue('filed1','value1',row,'ctx') //设置在指定行字段值，同时传入自定义数据
```
<a name="DataTable.isEnable"></a>

#### DataTable.isEnable([fieldName]) ⇒ <code>boolean</code>
判断DataTable或指定字段是否可修改

**返回值**: <code>boolean</code> - DataTable/指定字段是否可修改  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [fieldName] | <code>string</code> | 需要进行判断的字段值 |

**Example**  
```js
datatable.isEnable() //获取datatable是否可修改
datatable.isEnable('field1') //获取字段field1是否可修改
```
<a name="DataTable.setEnable"></a>

#### DataTable.setEnable(enable)
设置DataTable是否可修改


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| enable | <code>boolean</code> | true表示可修改，否则表示不可修改 |

**Example**  
```js
datatable.setEnable(true)
```
<a name="DataTable.getCurrentRow"></a>

#### DataTable.getCurrentRow() ⇒ <code>null</code> &#124; <code>u.Row</code>
获取DataTable对象的当前行

**返回值**: <code>null</code> &#124; <code>u.Row</code> - DataTable对象的当前行  
**Example**  
```js
datatable.getCurrentRow()
```
<a name="DataTable.getCurrentIndex"></a>

#### DataTable.getCurrentIndex() ⇒ <code>number</code>
获取DataTable对象的当前行对应的index

**返回值**: <code>number</code> - DataTable对象的当前行对应的index  
**Example**  
```js
datatable.getCurrentIndex()
```
<a name="DataTable.getData"></a>

#### DataTable.getData() ⇒ <code>array</code>
获取DataTable的数据信息

**返回值**: <code>array</code> - 数据信息对应的数组，每项对应一条数据  
**Example**  
```js
datatable.getData()
```
<a name="DataTable.getDataByRule"></a>

#### DataTable.getDataByRule(rule) ⇒ <code>array</code>
按照特定规则获取数据

**返回值**: <code>array</code> - 按照规则获取到的数据信息  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| rule | <code>string</code> | DataTable.SUBMIT.current('current') ：当前选中行 DataTable.SUBMIT.focus('focus') ：当前focus行 DataTable.SUBMIT.all('all') ：所有行 DataTable.SUBMIT.select('select') ：当前页选中行 DataTable.SUBMIT.change('change') ：发生改变的行 DataTable.SUBMIT.empty('empty') ：不获取数据，返回空数组 DataTable.SUBMIT.allSelect('allSelect') ：所有页选中行 DataTable.SUBMIT.allPages('allPages') ：所有页的数据 |

**Example**  
```js
datatable.getDataByRule(‘all’)
```
<a name="DataTable.getRow"></a>

#### DataTable.getRow(index) ⇒ <code>object</code>
根据索引获取指定行数据信息

**返回值**: <code>object</code> - 获取到的指定行数据信息  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 需要获取的数据信息的索引 |

**Example**  
```js
datatable.getRow(1)
```
<a name="DataTable.getRowByRowId"></a>

#### DataTable.getRowByRowId(rowid) ⇒ <code>Row</code>
根据rowid获取Row对象


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| rowid | <code>string</code> | 需要获取的Row对应的rowid |

**Example**  
```js
datatable.getRowByRowId('rowid')
```
<a name="DataTable.getRowIndex"></a>

#### DataTable.getRowIndex(需要获取索引的row对象) ⇒ <code>\*</code>
获取Row对象对应的索引


| 参数 | 类型 |
| --- | --- |
| 需要获取索引的row对象 | <code>u.Row</code> |

**Example**  
```js
var row = datatable.getRow(1)
datatable.getRowIndex(row) // 1
```
<a name="DataTable.getRowsByField"></a>

#### DataTable.getRowsByField(field, value) ⇒ <code>array</code>
根据字段及字段值获取所有数据行

**返回值**: <code>array</code> - 根据字段及字段值获取的所有数据行  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| field | <code>string</code> | 需要获取行的对应字段 |
| value | <code>string</code> | 需要获取行的对应字段值 |

**Example**  
```js
datatable.getRowsByField('field1','value1')
```
<a name="DataTable.getRowByField"></a>

#### DataTable.getRowByField(field, value) ⇒ <code>u.Row</code>
根据字段及字段值获取第一条数据行

**返回值**: <code>u.Row</code> - 根据字段及字段值获取第一条数据行  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| field | <code>string</code> | 需要获取行的对应字段 |
| value | <code>string</code> | 需要获取行的对应字段值 |

**Example**  
```js
datatable.getRowByField('field1','value1')
```
<a name="DataTable.getAllRows"></a>

#### DataTable.getAllRows() ⇒ <code>array</code>
获取当前页的所有数据行

**返回值**: <code>array</code> - 获取到的数据行  
**Example**  
```js
datatable.getAllRows()
```
<a name="DataTable.getAllPageRows"></a>

#### DataTable.getAllPageRows() ⇒ <code>array</code>
获取所有页的所有数据行

**返回值**: <code>array</code> - 获取到的数据行  
**Example**  
```js
datatable.getAllPageRows()
```
<a name="DataTable.getChangedDatas"></a>

#### DataTable.getChangedDatas(withEmptyRow) ⇒ <code>array</code>
获取发生变化的数据信息

**返回值**: <code>array</code> - 发生变化的数据信息  

| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| withEmptyRow | <code>boolean</code> | <code>false</code> | 未发生变化的数据是否使用空行代替，true表示以空行代替未发生变化行，false相反 |

**Example**  
```js
datatable.getChangedDatas()
```
<a name="DataTable.getChangedRows"></a>

#### DataTable.getChangedRows() ⇒ <code>array</code>
获取发生改变的Row对象

**返回值**: <code>array</code> - 发生改变的Row对象  
**Example**  
```js
datatable.getChangedRows()
```
<a name="DataTable.getValue"></a>

#### DataTable.getValue(fieldName, [row]) ⇒ <code>string</code>
根据字段获取对应Row对象的字段值

**返回值**: <code>string</code> - 获取到的字段值  

| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| fieldName | <code>string</code> |  | 需要获取的值对应的字段 |
| [row] | <code>u.Row</code> | <code>默认为当前行</code> | 对应的数据行 |

**Example**  
```js
datatable.getValue('field1')
var row = datatable.getRow(1)
datatable.getValue('field1',row)
```
<a name="DataTable.getIndexByRowId"></a>

#### DataTable.getIndexByRowId(rowId)
根据行号获取行索引


| 参数 | 类型 |
| --- | --- |
| rowId | <code>String</code> |

**Example**  
```js
datatable.getIndexByRowId('rowid')
```
<a name="DataTable.getAllDatas"></a>

#### DataTable.getAllDatas() ⇒ <code>array</code>
获取所有行数据信息

**返回值**: <code>array</code> - 所有行数据信息  
**Example**  
```js
datatable.getAllDatas()
```
<a name="DataTable.getRowIdsByIndices"></a>

#### DataTable.getRowIdsByIndices(indices) ⇒ <code>array</code>
根据索引获取rowid

**返回值**: <code>array</code> - 获取到的rowid  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| indices | <code>array</code> | 需要获取rowid的索引值 |

**Example**  
```js
datatable.getRowIdsByIndices([1,2,5])
```
<a name="DataTable.getFocusRow"></a>

#### DataTable.getFocusRow() ⇒ <code>u.Row</code>
获取焦点行

**返回值**: <code>u.Row</code> - 焦点行  
**Example**  
```js
datatable.getFocusRow()
```
<a name="DataTable.getFocusIndex"></a>

#### DataTable.getFocusIndex() ⇒ <code>number</code>
获取焦点行索引

**返回值**: <code>number</code> - 焦点行索引  
**Example**  
```js
datatable.getFocusIndex()
```
<a name="DataTable.getMeta"></a>

#### DataTable.getMeta([fieldName], [key]) ⇒ <code>object</code>
获取meta信息

**返回值**: <code>object</code> - meta信息  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [fieldName] | <code>string</code> | 需要获取的字段 |
| [key] | <code>string</code> | 需要获取的字段指定meta信息 |

**Example**  
```js
datatable.getMeta() // 获取所有meta信息
datatable.getMeta('field1') // 获取field1所有meta信息
datatable.getMeta('field1','type') // 获取field1的key信息
```
<a name="DataTable.getRowMeta"></a>

#### DataTable.getRowMeta([fieldName], [key]) ⇒ <code>object</code>
获取当前行的meta信息，如果不存在当前行则获取DataTable的meta信息

**返回值**: <code>object</code> - meta信息  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [fieldName] | <code>string</code> | 需要获取的字段 |
| [key] | <code>string</code> | 需要获取的字段指定meta信息 |

**Example**  
```js
datatable.getRowMeta() // 获取当前行所有meta信息
datatable.getRowMeta('field1') // 获取当前行field1所有meta信息
datatable.getRowMeta('field1','type') // 获取当前行field1的key信息
```
<a name="DataTable.getParam"></a>

#### DataTable.getParam(key) ⇒ <code>\*</code>
获取参数参数值

**返回值**: <code>\*</code> - 参数参数值  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| key | <code>string</code> | 参数对应的key |

**Example**  
```js
datatable.getParam('param1')
```
<a name="DataTable.getSelectedIndex"></a>

#### DataTable.getSelectedIndex() ⇒ <code>number</code>
获取选中行索引，多选时，只返回第一个行索引

**返回值**: <code>number</code> - 选中行索引  
**Example**  
```js
datatable.getSelectedIndex()
```
<a name="DataTable.getSelectedIndices"></a>

#### DataTable.getSelectedIndices() ⇒ <code>array</code>
获取选中的所有行索引数组

**返回值**: <code>array</code> - 所有行索引数组  
**Example**  
```js
datatable.getSelectedIndices()
```
<a name="DataTable.getSelectedDatas"></a>

#### DataTable.getSelectedDatas([withEmptyRow]) ⇒ <code>array</code>
获取选中行的数据信息

**返回值**: <code>array</code> - 发生变化的数据信息  

| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| [withEmptyRow] | <code>boolean</code> | <code>false</code> | 未选中的数据是否使用空行代替，true表示以空行代替未选中行，false相反 |

**Example**  
```js
datatable.getSelectedDatas()
datatable.getSelectedDatas(true)
```
<a name="DataTable.getSelectedRows"></a>

#### DataTable.getSelectedRows() ⇒ <code>array</code>
获取选中的Row对象

**返回值**: <code>array</code> - 选中的Row对象  
**Example**  
```js
datatable.getSelectedRows()
```
<a name="DataTable.getSimpleData"></a>

#### DataTable.getSimpleData([options]) ⇒ <code>array</code>
获取数据信息，只获取字段名与字段值

**返回值**: <code>array</code> - 获取到的数据信息  

| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| [options] | <code>object</code> |  | [description] |
| [options.type] | <code>string</code> | <code>&quot;all&quot;</code> | 获取数据的规则 all：所有数据 current：当前行数据 focus：焦点行数据 select：选中行数据 change：发生改变的数据 |
| [options.fields] | <code>array</code> |  | 需要获取数据的字段名数组 |

**Example**  
```js
datatable.getSimpleData() // 获取所有数据信息
datatable.getSimpleData({type:'current'}) // 获取当前行数据信息
datatable.getSimpleData({type:'current','fields':['filed1','field3']}) // 获取当前行field1和filed3数据信息
```
<a name="DataTable.setMeta"></a>

#### DataTable.setMeta(fieldName, key, value)
设置meta信息


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 需要设置meta信息的字段名 |
| key | <code>string</code> | meta信息的key |
| value | <code>string</code> | meta信息的值 |

**Example**  
```js
datatable.setMeta('filed1','type','string')
```
<a name="DataTable.updateMeta"></a>

#### DataTable.updateMeta(meta)
更新meta信息


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| meta | <code>object</code> | 需要更新的meta信息 |

**Example**  
```js
var metaObj = {supplier: {meta: {precision:'3', default: '0239900x', display:'显示名称'}}}
datatable.updateMeta(metaObj)
```
<a name="DataTable.addParam"></a>

#### DataTable.addParam(key, value)
增加参数参数


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| key | <code>string</code> | 需要增加的key值 |
| value | <code>\*</code> | 需要增加的具体指 |

**Example**  
```js
datatable.addParam('precision','3')
```
<a name="DataTable.addParams"></a>

#### DataTable.addParams(params)
增加多个参数参数


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| params | <code>object</code> | 需要增加的参数对象 |

**Example**  
```js
var paramsObj = {
 'precision':'3',
 'default':'1.234'
}
datatable.addParams(paramsObj)
```
<a name="DataTable.refSelectedRows"></a>

#### DataTable.refSelectedRows(fieldName)
为选中行绑定监听，当选中行发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |

**Example**  
```js
datatable.refSelectedRows().subscribe(function(){})
```
<a name="DataTable.ref"></a>

#### DataTable.ref(fieldName)
为某个字段绑定监听，当字段发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |

**Example**  
```js
datatable.ref('field1').subscribe(function(){})
```
<a name="DataTable.refMeta"></a>

#### DataTable.refMeta(fieldName, key)
绑定字段属性，当字段属性发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |
| key | <code>string</code> | 绑定的属性key |

**Example**  
```js
datatable.refMeta('field1','type').subscribe(function(){})
```
<a name="DataTable.refRowMeta"></a>

#### DataTable.refRowMeta(fieldName, key)
绑定当前行的字段属性，当字段属性发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |
| key | <code>string</code> | 绑定的属性key |

**Example**  
```js
datatable.refRowMeta('field1','type').subscribe(function(){})
```
<a name="DataTable.refEnable"></a>

#### DataTable.refEnable(fieldName)
绑定字段是否可修改属性，当字段可修改属性发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |

**Example**  
```js
datatable.refEnable('field1').subscribe(function(){})
```
<a name="DataTable.removeRowByRowId"></a>

#### DataTable.removeRowByRowId(rowId)
根据rowId删除指定行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| rowId | <code>string</code> | 需要删除行的rowId |

**Example**  
```js
datatable.removeRowByRowId('rowid1')
```
<a name="DataTable.removeRow"></a>

#### DataTable.removeRow(index)
根据索引删除指定行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 需要删除行的索引 |

**Example**  
```js
datatable.removeRow(1)
```
<a name="DataTable.removeAllRows"></a>

#### DataTable.removeAllRows()
删除所有行

**Example**  
```js
datatable.removeAllRows();
```
<a name="DataTable.removeRows"></a>

#### DataTable.removeRows(indices)
根据索引数据删除多条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| indices | <code>array</code> | 需要删除的数据行对应索引数组 |

**Example**  
```js
datatable.removeRows([1,2])
```
<a name="DataTable.clear"></a>

#### DataTable.clear()
清空datatable的所有数据以及分页数据以及index

**Example**  
```js
datatable.clear()
```
<a name="DataTable.addRow"></a>

#### DataTable.addRow(row)
在最后位置添加一条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| row | <code>u.Row</code> | 数据行 |

**Example**  
```js
var row1 = new Row({parent: datatable})
row1.setData({
 field1: 'value1',
 field2: 'value2'
})
datatable.addRow(row1)
```
<a name="DataTable.addRows"></a>

#### DataTable.addRows(rows)
在最后位置添加多条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| rows | <code>array</code> | 数据行数组 |

**Example**  
```js
var row1 = new Row({parent: datatable})
row1.setData({
 field1: 'value1',
 field2: 'value2'
})
var row2 = new Row({parent: datatable})
row2.setData({
 field1: 'value11',
 field2: 'value22'
})
datatable.addRow([row1,row2])
```
<a name="DataTable.insertRow"></a>

#### DataTable.insertRow(index, row)
在指定索引位置添加一条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 指定索引 |
| row | <code>u.Row</code> | 数据行 |

**Example**  
```js
var row1 = new Row({parent: datatable})
row1.setData({
 field1: 'value1',
 field2: 'value2'
})
datatable.insertRow(1,row1)
```
<a name="DataTable.insertRows"></a>

#### DataTable.insertRows(index, rows)
在指定索引位置添加多条数据行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 指定索引 |
| rows | <code>array</code> | 数据行数组 var row1 = new Row({parent: datatable}) row1.setData({  field1: 'value1',  field2: 'value2' }) var row2 = new Row({parent: datatable}) row2.setData({  field1: 'value11',  field2: 'value22' }) datatable.insertRows(1,[row1,row2]) |

<a name="DataTable.createEmptyRow"></a>

#### DataTable.createEmptyRow() ⇒ <code>u.Row</code>
创建空行

**返回值**: <code>u.Row</code> - 空行对象  
**Example**  
```js
datatable.createEmptyRow();
```
<a name="DataTable.setAllRowsSelect"></a>

#### DataTable.setAllRowsSelect()
设置所有行选中

**Example**  
```js
datatable.setAllRowsSelect()
```
<a name="DataTable.setRowSelect"></a>

#### DataTable.setRowSelect(index)
根据索引设置选中行，清空之前已选中的所有行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 需要选中行的索引 |

**Example**  
```js
datatable.setRowSelect(1)
```
<a name="DataTable.setRowsSelect"></a>

#### DataTable.setRowsSelect(indices)
根据索引数组设置选中行，清空之前已选中的所有行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| indices | <code>array</code> | 需要选中行的索引数组 |

**Example**  
```js
datatable.setRowsSelect([1,2])
```
<a name="DataTable.addRowSelect"></a>

#### DataTable.addRowSelect(index)
根据索引添加选中行，不会清空之前已选中的行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 需要选中行的索引 |

**Example**  
```js
datatable.addRowSelect(1)
```
<a name="DataTable.addRowsSelect"></a>

#### DataTable.addRowsSelect(indices)
根据索引数组添加选中行，不会清空之前已选中的行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| indices | <code>array</code> | 需要选中行的索引数组 |

**Example**  
```js
datatabel.addRowsSelect([1,2])
```
<a name="DataTable.setAllRowsUnSelect"></a>

#### DataTable.setAllRowsUnSelect([options])
全部取消选中


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [options] | <code>object</code> | 可选参数 |
| [options.quiet] | <code>boolean</code> | 如果为true则不触发事件，否则触发事件 |

**Example**  
```js
datatable.setAllRowsUnSelect() // 全部取消选中
datatable.setAllRowsUnSelect({quiet:true}) // 全部取消选中,不触发事件
```
<a name="DataTable.setRowUnSelect"></a>

#### DataTable.setRowUnSelect(index)
根据索引取消选中


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> | 需要取消选中的行索引 |

**Example**  
```js
datatable.setRowUnSelect(1)
```
<a name="DataTable.setRowsUnSelect"></a>

#### DataTable.setRowsUnSelect(indices)
根据索引数组取消选中


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| indices | <code>array</code> | 需要取消选中的行索引数组 |

**Example**  
```js
datatable.setRowsUnSelect([1,2])
```
<a name="DataTable.toggleAllSelect"></a>

#### DataTable.toggleAllSelect()
当全部选中时取消选中，否则全部选中

<a name="DataTable.setRowFocus"></a>

#### DataTable.setRowFocus(index, [quiet], [force])
设置焦点行


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| index | <code>number</code> &#124; <code>u.Row</code> | 行对象或者行index |
| [quiet] | <code>boolean</code> | 如果为true则不触发事件，否则触发事件 |
| [force] | <code>boolean</code> | 如果为true当index行与已focus的行相等时，仍然触发事件，否则不触发事件 |

**Example**  
```js
datatable.setRowFocus(1) // 设置第二行为焦点行
datatable.setRowFocus(1,true) // 设置第二行为焦点行，不触发事件
datatable.setRowFocus(1,false,true) // 设置第二行为焦点行，如果当前焦点行为第二行，仍旧触发事件
```
<a name="DataTable.setRowUnFocus"></a>

#### DataTable.setRowUnFocus()
焦点行反选

**Example**  
```js
datatable.setRowUnFocus()
```
<a name="DataTable.setSimpleData"></a>

#### DataTable.setSimpleData(data, [options])
设置数据, 只设置字段值


| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| data | <code>array</code> |  | 数据信息 |
| [options] | <code>boject</code> |  | 可配置参数 |
| [options.unSelect] | <code>boject</code> | <code>true</code> | 是否默认选中第一行，如果为true则不选中第一行，否则选中第一行 |

**Example**  
```js
var data = [{
  filed1:'value1',
  field2:'value2'
},{
  filed1:'value11',
  field2:'value21'
}]
datatable.setSimpleData(data)
datatable.setSimpleData(data,{unSelect:false})
```
<a name="DataTable.addSimpleData"></a>

#### DataTable.addSimpleData(data, status)
追加数据, 只设置字段值


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| data | <code>array</code> | 数据信息 |
| status | <code>string</code> | 追加数据信息的状态，参照Row对象的状态介绍 |

**Example**  
```js
var data = [{
  filed1:'value1',
  field2:'value2'
},{
  filed1:'value11',
  field2:'value21'
}]
datatable.addSimpleData(data,Row.STATUS.NEW)
```
<a name="DataTable.on"></a>

#### DataTable.on(name, [callback], [one]) ⇒ <code>[DataTable](#DataTable)</code>
为DataTable对象添加监听

**返回值**: <code>[DataTable](#DataTable)</code> - 当前的DataTable对象  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| name | <code>string</code> &#124; <code>array</code> &#124; <code>object</code> | 针对不同用法分别对应监听名称、监听名称对应的数组、监听名称及对应的回调组成的对象 |
| [callback] | <code>function</code> | 监听对应的回调函数 |
| [one] | <code>boolean</code> | 是否只执行一次监听，为true则表示只执行一次回调函数，否则每次触发监听都是执行回调函数 |

**Example**  
```js
datatable.on(u.DataTable.ON_ROW_FOCUS, function() {}) // 普通
datatable.on([u.DataTable.ON_INSERT, u.DataTable.ON_DELETE], function() {}) // 数组
datatable.on({u.DataTable.ON_INSERT: function() {}, u.DataTable.ON_DELETE: function() {}}) // map
```
<a name="DataTable.off"></a>

#### DataTable.off(name, [callback]) ⇒ <code>[DataTable](#DataTable)</code>
为DataTable对象取消监听

**返回值**: <code>[DataTable](#DataTable)</code> - 当前的DataTable对象  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| name | <code>string</code> &#124; <code>array</code> &#124; <code>object</code> | 针对不同用法分别对应监听名称、监听名称对应的数组、监听名称及对应的回调组成的对象 |
| [callback] | <code>function</code> | 监听对应的回调函数 |

**Example**  
```js
datatable.off(u.DataTable.ON_ROW_FOCUS, function() {}) // 普通
datatable.off([u.DataTable.ON_INSERT, u.DataTable.ON_DELETE], function() {}) // 数组
datatable.off({u.DataTable.ON_INSERT: function() {}, u.DataTable.ON_DELETE: function() {}}) // map
```
<a name="DataTable.one"></a>

#### DataTable.one(name, [callback])
为DataTable对象添加只执行一次的监听


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| name | <code>string</code> &#124; <code>array</code> &#124; <code>object</code> | 针对不同用法分别对应监听名称、监听名称对应的数组、监听名称及对应的回调组成的对象 |
| [callback] | <code>function</code> | 监听对应的回调函数 |

**Example**  
```js
datatable.one(u.DataTable.ON_ROW_FOCUS, function() {}) // 普通
datatable.one([u.DataTable.ON_INSERT, u.DataTable.ON_DELETE], function() {}) // 数组
datatable.one({u.DataTable.ON_INSERT: function() {}, u.DataTable.ON_DELETE: function() {}}) // map
```
<a name="DataTable.trigger"></a>

#### DataTable.trigger(name) ⇒ <code>[DataTable](#DataTable)</code>
触发DataTable对象绑定的事件监听

**返回值**: <code>[DataTable](#DataTable)</code> - 当前的DataTable对象  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| name | <code>string</code> | 需要触发的事件监听对应的名称 |

**Example**  
```js
datatable.trigger('valuechange')
```

<a name="Row"></a>

### Row : <code>object</code>
前端数据模型行对象


* [Row](#Row) : <code>object</code>
    * _instance_
        * [.rowId](#Row+rowId) : <code>string</code>
        * [.status](#Row+status) : <code>string</code>
        * [.parent](#Row+parent)
    * _static_
        * [.setValue(fieldName, value, [ctx])](#Row.setValue)
        * [.setData(data, [subscribe], [options])](#Row.setData)
        * [.getValue(fieldName)](#Row.getValue) ⇒ <code>string</code>
        * [.getData()](#Row.getData) ⇒ <code>object</code>
        * [.getSimpleData([options])](#Row.getSimpleData) ⇒ <code>object</code>
        * [.setSimpleData(data, [status])](#Row.setSimpleData)
        * [.toggleSelect([type])](#Row.toggleSelect)
        * [.getMeta(fieldName, key, [fetchParent])](#Row.getMeta) ⇒ <code>string</code>
        * [.setMeta(fieldName, key, value)](#Row.setMeta)
        * [.ref(fieldName)](#Row.ref)
        * [.refMeta(fieldName, key)](#Row.refMeta)
        * [.refCombo(fieldName, datasource)](#Row.refCombo)
        * [.refDate(fieldName, format)](#Row.refDate)

<a name="Row+rowId"></a>

#### row.rowId : <code>string</code>
当前行的唯一标识

<a name="Row+status"></a>

#### row.status : <code>string</code>
当前行的状态
Row.STATUS.NORMAL('nrm') ：前后端都存在并且保持一致
Row.STATUS.UPDATE('upd') ：前后端都存在并且前端进行了修改
Row.STATUS.NEW('new') ：后端不存在，前端存在的数据
Row.STATUS.DELETE('del') ：后端请求返回的状态，前端判断为此状态则将数据删除
Row.STATUS.FALSE_DELETE('fdel') ：后端存在，前端不存在的数据

**Default**: <code>&quot;Row.STATUS.NEW&quot;</code>  
<a name="Row+parent"></a>

#### row.parent
当前行对应的DataTable对象

<a name="Row.setValue"></a>

#### Row.setValue(fieldName, value, [ctx])
设置对应字段的值


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 需要设置的字段 |
| value | <code>string</code> | 需要设置的值 |
| [ctx] | <code>\*</code> | 自定义属性，在valuechange监听传入对象中可通过ctx获取此处设置 |

**Example**  
```js
row.setValue('filed1','value1') // 设置字段值
row.setValue('filed1','value1','ctx') //设置字段值，同时传入自定义数据
```
<a name="Row.setData"></a>

#### Row.setData(data, [subscribe], [options])
设置row的数据信息


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| data | <code>object</code> | 需要设置的配置信息 |
| [subscribe] | <code>boolean</code> | 是否触发监听，true表示触发监听 |
| [options] | <code>object</code> | 设置数据信息是的配置参数 |
| [options.fieldFlag] | <code>boolean</code> | 未设置的meta是否进行存储，如果为true则未设置的meta也进行存储 var data = {   filed1:'value1',   field2:'value2' } row.setData(data) row.setData(data,false) row.setData(data),false,{fieldFlag:true}) |

<a name="Row.getValue"></a>

#### Row.getValue(fieldName) ⇒ <code>string</code>
获取row中某一字段的值

**返回值**: <code>string</code> - 字段值  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 字段名 |

**Example**  
```js
row.getValue('field1')
```
<a name="Row.getData"></a>

#### Row.getData() ⇒ <code>object</code>
获取数据信息

**返回值**: <code>object</code> - 格式如下：{'id': this.rowId, 'status': this.status, data: data}  
**Example**  
```js
row.getData()
```
<a name="Row.getSimpleData"></a>

#### Row.getSimpleData([options]) ⇒ <code>object</code>
获取数据信息

**返回值**: <code>object</code> - 数据信息  

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [options] | <code>object</code> | 获取数据信息时的配置参数 |
| [options.fields] | <code>array</code> | 获取数据信息时是否制定字段值 |

**Example**  
```js
row.getSimpleData()
row.getSimpleData({fields:['field1','field2']})
```
<a name="Row.setSimpleData"></a>

#### Row.setSimpleData(data, [status])
设置数据, 只设置字段值


| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| data | <code>object</code> |  | 数据信息 |
| [status] | <code>boject</code> | <code>nrm</code> | 数据行状态 |

**Example**  
```js
var data = {
  filed1:'value1',
  field2:'value2'
}
datatable.setSimpleData(data)
datatable.setSimpleData(data,'upd')
```
<a name="Row.toggleSelect"></a>

#### Row.toggleSelect([type])
切换数据行的选中状态


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| [type] | <code>boolean</code> | 执行选中操作时，如果为single则取消其他行的选中状态，否则只修改当前行的选中状态 |

**Example**  
```js
row.toggleSelect()
row.toggleSelect('single')
row.toggleSelect('multi')
```
<a name="Row.getMeta"></a>

#### Row.getMeta(fieldName, key, [fetchParent]) ⇒ <code>string</code>
获取字段的属性

**返回值**: <code>string</code> - 属性值  

| 参数 | 类型 | Default | 描述 |
| --- | --- | --- | --- |
| fieldName | <code>string</code> |  | 字段名 |
| key | <code>string</code> |  | 属性名 |
| [fetchParent] | <code>boolean</code> | <code>false</code> | 未定义时是否去DataTable对象查找，为true则未定义时去DataTable对象查找 |

**Example**  
```js
row.getMeta('field1','type')
row.getMeta('field1','type',true)
```
<a name="Row.setMeta"></a>

#### Row.setMeta(fieldName, key, value)
设置meta信息


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 需要设置meta信息的字段名 |
| key | <code>string</code> | meta信息的key |
| value | <code>string</code> | meta信息的值 |

**Example**  
```js
row.setMeta('filed1','type','string')
```
<a name="Row.ref"></a>

#### Row.ref(fieldName)
为某个字段绑定监听，当字段发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |

**Example**  
```js
row.ref('field1').subscribe(function(){})
```
<a name="Row.refMeta"></a>

#### Row.refMeta(fieldName, key)
绑定字段属性，当字段属性发生改变时触发对应方法


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |
| key | <code>string</code> | 绑定的属性key |

**Example**  
```js
row.refMeta('field1','type').subscribe(function(){})
```
<a name="Row.refCombo"></a>

#### Row.refCombo(fieldName, datasource)
为某个字段绑定监听，当字段发生改变时触发对应方法，针对下拉字段根据key转化为对应的value


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |
| datasource | <code>string</code> | 下拉数据源变量名 |

**Example**  
```js
row.refCombo('field1','source1').subscribe(function(){})
```
<a name="Row.refDate"></a>

#### Row.refDate(fieldName, format)
为某个字段绑定监听，当字段发生改变时触发对应方法，针对日期字段进行格式化


| 参数 | 类型 | 描述 |
| --- | --- | --- |
| fieldName | <code>string</code> | 绑定的字段名 |
| format | <code>string</code> | 格式化规则 |

**Example**  
```js
row.refDate('field1','YYYY-MM-DD').subscribe(function(){})
```



## Grid 属性API

### id

类型     | 默认值  | 说明
------ | ---- | -------
string | grid | 表格控件的标识

### cancelFocus

类型      | 默认值   | 说明
------- | ----- | ---------------------------------------------------
boolean | false | 第二次点击行是否取消focus效果。true表示取消focus效果，false表示不取消focus效果

### cancelSelect

类型      | 默认值   | 说明
------- | ----- | ------------------------------------------------------
boolean | false | 第二次点击行是否取消select效果。true表示取消select效果，false表示不取消select效果

### showHeader

类型      | 默认值  | 说明
------- | ---- | ------------------------------
boolean | true | 是否显示表头。true表示显示表头，false表示不显示表头

### showNumCol

类型      | 默认值   | 说明
------- | ----- | ---------------------------------
boolean | false | 是否显示数字列。true表示显示数字列，false表示不显示数字列

### multiSelect

类型      | 默认值   | 说明
------- | ----- | ----------------------------------------
boolean | false | 是否显示复选框以支持复选功能。true表示显示复选框，false表示不显示复选框

### rowHeight

类型      | 默认值   | 说明
------- | ----- | ----------------------------------------
integer | 44 | 内容区数据行的行高

### sumRowHeight

类型     | 默认值     | 说明
------ | ------- | ----------------------------------------------
integer | 44 | 内容区合计行的行高

### columnMenu

类型      | 默认值  | 说明
------- | ---- | ----------------------------------------------------------------
boolean | true | 是否显示表头操作按钮，通过表头操作按钮可以动态设置数据列是否显示。true表示显示表头操作按钮，false表示不显示表头操作按钮

### canDrag

类型      | 默认值  | 说明
------- | ---- | --------------------------------------------
boolean | true | 是否支持拖动表头以修改数据列宽度。true表示支持拖动功能，false表示不支持拖动功能

### maxHeaderLevel

类型      | 默认值 | 说明
------- | --- | -------------------------
integer | 1   | 多级表头情况下，表头的最高层级。目前只支持最大为2

### overWidthHiddenColumn

类型      | 默认值   | 说明
------- | ----- | --------------------------------------------------------------
boolean | false | 表格的整体宽度不足以显示所有数据列时是否自动隐藏超出部分的数据列。true表示超出时自动隐藏，false表示超出时不自动隐藏

### sortable

类型      | 默认值  | 说明
------- | ---- | ------------------------------------------
boolean | true | 是否支持点击表头进行排序功能。true表示支持排序功能，false表示不支持排序功能

### showSumRow

类型      | 默认值   | 说明
------- | ----- | ------------------------------------------
boolean | false | 是否支持合计功能以显示合计行。true表示支持合计功能，false表示不支持合计功能

### sumRowFirst

类型      | 默认值   | 说明
------- | ----- | ------------------------------------------
boolean | false | 合计行是否显示在第一行，true表示显示在第一行，false表示显示在最后一行

### sumRowFixed

类型      | 默认值   | 说明
------- | ----- | ------------------------------------------
boolean | false | 合计行是否固定在头部/尾部，不随滚动条滚动

### canSwap

类型      | 默认值  | 说明
------- | ---- | ---------------------------------------------
boolean | true | 是否支持拖动表头以交换数据列的位置。true表示支持交换功能，false表示不支持交换功能

### showTree

类型      | 默认值   | 说明
------- | ----- | -----------------------------------------
boolean | false | 是否支持以树表形式进行展示。true表示支持树表功能，false表示不支持树表功能

### autoExpand

类型      | 默认值  | 说明
------- | ---- | -----------------------------------------------
boolean | true | 树表形式展示时是否默认展开所有节点。true表示默认展开所有节点，false表示默认不展开节点

### needTreeSort

类型      | 默认值   | 说明
------- | ----- | -----------------------------------------------------------------------------------------------
boolean | false | 树表形式下是否需要对传入数据进行排序，此设置是为了优化性能。如果传入数据是无序的则设置为true，如果可以保证先传入父节点后传入子节点则设置为false提高性能。目前只支持为false的情况

### needLocalStorage

类型      | 默认值   | 说明
------- | ----- | -----------------------------------------------------------------------------------------
boolean | false | 是否使用前端缓存，使用前端缓存的情况会在浏览器保存数据列的宽度、是否显示、位置等信息，再次进入页面会按照上次的状态进行显示。true表示使用前端缓存,false表示不使用前端缓存

### noScroll

类型      | 默认值   | 说明
------- | ----- | ----------------------------------------------------------------------------------------------------
boolean | false | 是否显示滚动条。如果数据列宽度中存在百分比的设置则此参数自动修改为true。true表示不显示滚动条，数据列的宽度会根据整体宽度重新计算,false表示按照默认显示，如果列宽度超过整体宽度则显示滚动条

### contentSelect

类型      | 默认值  | 说明
------- | ---- | ----------------------------------------------------------
boolean | true | 点击内容区是否执行选中逻辑，单选情况下则此参数修改为true。true表示执行选中逻辑,false表示不执行选中逻辑

### contentFocus

类型      | 默认值  | 说明
------- | ---- | --------------------------------------------------
boolean | true | 点击内容区是否执行focus逻辑。true表示执行focus逻辑,false表示不执行focus逻辑

### showEditIcon

类型      | 默认值   | 说明
------- | ----- | ---------------------------------------------
boolean | false | 数据列可修改情况下是否显示编辑图标。true表示显示编辑图标,false表示不显示编辑图标

### editable

类型      | 默认值   | 说明
------- | ----- | ------------------------------------
boolean | false | 是否支持编辑功能。true表示支持编辑功能，false表示不支持编辑功能

### editType

类型     | 默认值     | 说明
------ | ------- | ----------------------------------------------
string | default | 设置编辑方式。default表示在数据行上进行编辑，form表示在单独的form区域进行编辑

### fixedFloat

类型     | 默认值     | 说明
------ | ------- | ----------------------------------------------
string | left | 固定列的对齐方式。left表示固定列在左侧显示，right表示固定列在右侧显示

### groupField

类型     | 默认值     | 说明
------ | ------- | ----------------------------------------------
string |  | 按照某个字段进行分组，需为表格中包含的field名称

### groupSumRow

类型     | 默认值     | 说明
------ | ------- | ----------------------------------------------
boolean | false | 存在分组字段的情况下，是否按照分组显示小计功能

## Grid 列属性API

### field

类型     | 默认值  | 说明
------ | ---- | -----------
string | null | 数据列对应的field

### width

类型      | 默认值 | 说明
------- | --- | ----------------------------------------
integer | 200 | 数据列显示的宽度，可支持百分比和数字两种方式。百分比情况下则内容区不显示滚动条。

### sortable

类型      | 默认值  | 说明
------- | ---- | ---------------------------------
boolean | true | 数据列是否支持排序。true表示支持排序，false表示不支持排序

### canDrag

类型      | 默认值  | 说明
------- | ---- | -------------------------------------
boolean | true | 数据列是否支持拖动修改宽度。true表示支持拖动，false表示不支持拖动

### fixed

类型      | 默认值   | 说明
------- | ----- | ---------------------------------------------
boolean | false | 是否为固定列。true表示此列为固定列，在表头前面固定显示，false，表示此列不为固定列

### visible

类型      | 默认值  | 说明
------- | ---- | --------------------------------
boolean | true | 是否显示。true表示此列进行显示，false表示此列不进行显示

### canVisible

类型      | 默认值  | 说明
------- | ---- | -----------------------------------------------------------
boolean | true | 是否可以通过表头功能设置数据列是否显示。true表示可以通过表头设置是否显示，false表示不可以通过表头设置是否显示

### sumCol

类型      | 默认值   | 说明
------- | ----- | --------------------------------------------
boolean | false | 表格支持合计功能时，是否计算合计。true表示需要计算合计，false表示不需要计算合计

### editable

类型      | 默认值  | 说明
------- | ---- | -----------------------------------------------
boolean | true | 表格支持修改过程时，数据列是否可以修改。true表示可以进行修改，false表示不可以进行修改

### editFormShow

类型      | 默认值  | 说明
------- | ---- | -----------------------------------------------------------------------
boolean | true | 在表格以form形式编辑时，数据列是否显示，此参数用于支持form编辑模式下可对未显示的数据列进行编辑。true表示显示，false表示不显示

### autoExpand

类型      | 默认值   | 说明
------- | ----- | -----------------------------------------------------
boolean | false | 数据列宽度是否需要自动扩展，只有最后一列需要设置为true。true表示自动扩展，false表示不自动扩展

### renderType

类型       | 默认值  | 说明
-------- | ---- | -------------------------------
function | null | 数据列的渲染方式，通过function创建数据列对应的编辑控件

**object属性说明**

属性             | 说明
-------------- | -----------------------------------
value          | 单元格对应的value值
element        | 单元格渲染时，组件提供的顶层div，自定义渲染内容在此div下进行渲染
gridObj        | 表格控件对象
row            | 单元格所在行对应的行对象，可获取所在行其他列信息
gridCompColumn | 单元格对应的列对象，可获取所在列的配置信息
rowIndex       | 单元格所在行的index

### editType

类型       | 默认值  | 说明
-------- | ---- | -------------------------------
function | null | 数据列的编辑方式，通过function创建数据列对应的编辑控件

**object属性说明**

属性       | 说明
-------- | -----------------------------------
value    | 单元格对应的value值
element  | 单元格编辑时，组件提供的顶层div，自定义编辑内容在此div下进行编辑
gridObj  | 表格控件对象
field    | 数据列对应的field
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### dataType

类型     | 默认值    | 说明
------ | ------ | ----------------------------------------------
string | String | 数据列的数据类型，支持：String, Date, Datetime, Int, Float

### format

类型     | 默认值    | 说明
------ | ------ | -----------------------------------------------------------
string | String | 数据列显示时的格式化方式。目前只对日期类型进行处理，例如：YYYY-MM-DD、YYYY-MM-DD hh:mm:ss

### headerLevel

类型      | 默认值 | 说明
------- | --- | -------------------
integer | 1   | header的层级，目前只支持最大2级

### hiddenLevel

类型      | 默认值 | 说明
------- | --- | --------------------------------------------------------
integer | 1   | 当表格属性overWidthHiddenColumn为true时，自动隐藏的优先级，数值越大，宽度不足时优先显示

## Grid 生命周期API

### onBeforeRowSelected

类型       | 说明
-------- | ---------------------------------------------------------------------------------------------------
function | 在数据行被选中之前触发，可在function中决定是否选中数据行，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onRowSelected

类型       | 说明
-------- | --------------------------------------
function | 在数据行被选中后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onBeforeRowUnSelected

类型       | 说明
-------- | ------------------------------------------------------------------------------------------------------
function | 在数据行取消选中之前触发，可在function中决定是否取消数据行选中，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onRowUnSelected

类型       | 说明
-------- | ---------------------------------------
function | 在数据行取消选中后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onBeforeAllRowSelected

类型       | 说明
-------- | -------------------------------------------------------------------------------------------------------------
function | 在点击表头复选框选中所有数据行之前触发，可在function中决定是否选中所有数据行，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性      | 说明
------- | -------
gridObj | 表格控件对象
rowObjs | 所有数据行对象

### onAllRowSelected

类型       | 说明
-------- | -----------------------------------------------
function | 在点击表头复选框选中所有数据行之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性      | 说明
------- | -------
gridObj | 表格控件对象
rowObjs | 所有数据行对象

### onBeforeAllRowUnSelected

类型       | 说明
-------- | -----------------------------------------------------------------------------------------------------------------
function | 在点击表头复选框取消选中所有数据行之前触发，可在function中决定是否取消选中所有数据行，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性      | 说明
------- | -------
gridObj | 表格控件对象
rowObjs | 所有数据行对象

### onAllRowUnSelected

类型       | 说明
-------- | -----------------------------------------------
function | 在点击表头复选框选中所有数据行之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性      | 说明
------- | -------
gridObj | 表格控件对象
rowObjs | 所有数据行对象

### onBeforeRowFocus

类型       | 说明
-------- | -----------------------------------------------------------------------------------------------------------
function | 在数据行触发focus之前触发，可在function中决定是否继续focus操作，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

### onRowFocus

类型       | 说明
-------- | -------------------------------------------
function | 在数据行触发focus之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onBeforeRowUnFocus

类型       | 说明
-------- | -----------------------------------------------------------------------------------------------------------
function | 在数据行取消focus之前触发，可在function中决定是否取消focus操作，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onRowUnFocus

类型       | 说明
-------- | -------------------------------------------
function | 在数据行取消focus之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onDblClickFun

类型       | 说明
-------- | --------------------------------------
function | 在数据行被双击时触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onBeforeValueChange

类型       | 说明
-------- | -----------------------------------------------------------------------------------------------------
function | 在对数据进行修改之前触发，可在function中决定是否进行数据修改，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

### onValueChange

类型       | 说明
-------- | ----------------------------------------
function | 在对数据进行修改之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | ------------
gridObj  | 表格控件对象
rowIndex | 数据行对应的index
field    | 数据改变对应的field
oldValue | 数据改变之前的值
newValue | 数据改变之后的值

### onBeforeClickFun

类型       | 说明
-------- | ---------------------------------------------------------------------------------------------------------------
function | 在数据行触发click之前触发，可在function中决定是否继续数据行的click操作，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### onBeforeEditFun

类型       | 说明
-------- | -------------------------------------------------------------------------------------------------------
function | 在数据行编辑操作之前触发，可在function中决定是否取消进行编辑操作，return true则继续当前操作，return false则取消当前操作，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index
colIndex | 数据列对应的index

### onRowHover

类型       | 说明
-------- | -----------------------------------------
function | 在数据行hover之后触发，调用时传入参数为object，object属性说明如下

**object属性说明**

属性       | 说明
-------- | -----------
gridObj  | 表格控件对象
rowObj   | 数据行对象
rowIndex | 数据行对应的index

### afterCreate

类型       | 说明
-------- | ---------------------------
function | 表格创建完成或者重新添加数据之后触发，调用时无传入参数

## Grid 方法API

### setRequired

**说明**

编辑模式化设置某列是否必输

**返回值**

无

**参数说明**

参数    | 类型      | 是否必须 | 说明
----- | ------- | ---- | -------------------------
field | string  | true | 需要设置的数据列对应的field
value | boolean | true | true表示设置为必输，false表示设置为非必输

### getColumnAttr

**说明**

获取field对应的column对象属性

**返回值**

对应的属性值

**参数说明**

参数    | 类型     | 是否必须 | 说明
----- | ------ | ---- | --------------
attr  | string | true | 属性名称
field | string | true | column对应的field

### getColumnByField

**说明**

根据field获取column对象

**返回值**

对应的column对象

**参数说明**

参数    | 类型     | 是否必须 | 说明
----- | ------ | ---- | ---------------------
field | stirng | true | 需要获取的column对象对应的field

### getIndexOfColumn

**说明**

获取column对象的index

**返回值**

对应的index

**参数说明**

参数     | 类型     | 是否必须 | 说明
------ | ------ | ---- | --------
column | object | true | column对象

### getVisibleIndexOfColumn

**说明**

获取column对象在显示的数据列中的index

**返回值**

对应的index

**参数说明**

参数     | 类型     | 是否必须 | 说明
------ | ------ | ---- | --------
column | object | true | column对象

### getNextVisibleInidexOfColumn

**说明**

获取column后面第一个显示列所在第几列

**返回值**

对应的index

**参数说明**

参数     | 类型     | 是否必须 | 说明
------ | ------ | ---- | --------
column | object | true | column对象

### setColumnVisibleByColumn

**说明**

通过column对象设置某列是否显示

**返回值**

无

**参数说明**

参数      | 类型      | 是否必须 | 说明
------- | ------- | ---- | -------------------------
column  | object  | true | column对象
visible | boolean | true | true表示设置为显示，false表示设置为不显示

### setColumnVisibleByIndex

**说明**

通过index设置某列是否显示

**返回值**

无

**参数说明**

参数      | 类型      | 是否必须 | 说明
------- | ------- | ---- | -------------------------
index   | integer | true | 数据列对应的index
visible | boolean | true | true表示设置为显示，false表示设置为不显示

### setCoulmnWidthByField

**说明**

通过field属性设置数据列宽度

**返回值**

无

**参数说明**

参数       | 类型     | 是否必须 | 说明
-------- | ------ | ---- | --------------
field    | string | true | 所需修改数据对应的field
newWidth | string | true | 所需修改数据的新宽度的数值

### setCoulmnWidth

**说明**

通过coulmn对象设置宽度

**返回值**

无

**参数说明**

参数       | 类型     | 是否必须 | 说明
-------- | ------ | ---- | -------------
column   | object | true | column对象
newWidth | string | true | 所需修改数据的新宽度的数值

### setDataSource

**说明**

设置表格控件的数据信息

**返回值**

无

**参数说明**

参数         | 类型     | 是否必须 | 说明
---------- | ------ | ---- | -----
dataSource | object | true | 数据信息。

**示例**

```
gridObj.setDataSource({
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
    }]
});
```

### setDataSourceFun1

**说明**

设置表格控件的数据信息与setDataSource传入格式不同

**返回值**

无

**参数说明**

参数         | 类型     | 是否必须 | 说明
---------- | ------ | ---- | -----
dataSource | object | true | 数据信息。

**示例**

```
gridObj.setDataSourceFun1({
    fields:['column1','column2','column3','column4','column5','column6'],
        values:[
        ["cl1","1","cl3","cl4","cl5","cl6"],
        ["cl12","2","cl32","cl42","cl52","cl62"],
        ["cl13","3","cl33","cl43","cl53","cl63"],
        ["cl14","4","cl34","cl44","cl54","cl64"],
        ["cl15","5","cl35","cl45","cl55","cl65"],
        ["cl16","6","cl36","cl46","cl56","cl66"]
        ]
});
```

### addOneRow

**说明**

添加一行数据

**返回值**

无

**参数说明**

参数    | 类型      | 是否必须  | 说明
----- | ------- | ----- | ---------
row   | object  | true  | 数据信息
index | integer | false | 需要插入数据的位置

**示例**

```
gridObj.addonerow({
        "column1": "value1",
        "column2": "value2",
        "column3": "value3"
    },1);
```

### addRows

**说明**

添加多行数据

**返回值**

无

**参数说明**

参数    | 类型      | 是否必须  | 说明
----- | ------- | ----- | ---------
rows  | array   | true  | 数据信息
index | integer | false | 需要插入数据的位置

**示例**

```
gridObj.addRows([{
        "column1": "value1",
        "column2": "value2",
        "column3": "value3"
    },{
        "column1": "value11",
        "column2": "value22",
        "column3": "value33"
    }],1);
```

### deleteOneRow

**说明**

删除某条数据

**返回值**

无

**参数说明**

参数    | 类型      | 是否必须 | 说明
----- | ------- | ---- | --------------
index | integer | true | 需要删除数据对应的index

### deleteRows

**说明**

删除多条数据

**返回值**

无

**参数说明**

参数     | 类型    | 是否必须 | 说明
------ | ----- | ---- | -----------------
indexs | array | true | 需要删除数据的index组成的数组

### updateRow

**说明**

修改某行数据

**返回值**

无

**参数说明**

参数    | 类型      | 是否必须 | 说明
----- | ------- | ---- | ----------
index | integer | true | 被修改行的index
row   | object  | true | 修改之后的数据信息

**示例**

```
gridObj.updateRow(1,{
        "column1": "value1",
        "column2": "value2",
        "column3": "value3"
    });
```

### updateValueAt

**说明**

修改某个单元格的数据

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须  | 说明
-------- | ------- | ----- | ------------------------------------------------------
rowIndex | integer | true  | 所需修改数据对应的行号
field    | string  | true  | 所需修改数据对应的field
value    | string  | true  | 修改之后的数据
force    | boolean | false | true表示不管数据是否发生改变，都执行update操作，false表示只有数据改变时才执行update操作

### setRowSelect

**说明**

设置某行选中

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | -----------
rowIndex | integer | true | 选中行对应的index

### setRowUnselect

**说明**

取消某行的选中状态

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | -------------
rowIndex | integer | true | 取消选中行对应的index

### setAllRowSelect

**说明**

设置所有行选中

**返回值**

无

### setAllRowUnSelect

**说明**

设置所有行取消选中

**返回值**

无

### getSelectRows

**说明**

获取所有选中行

**返回值**

所有选中行对象

### getSelectRowsIndex

**说明**

获取所有选中行对应的inex

**返回值**

所有选中行index

### setRowFocus

**说明**

设置某行为focus状态

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | --------------
rowIndex | integer | true | focus行对应的index

### setRowUnFocus

**说明**

取消某行的focus状态

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | ----------------
rowIndex | integer | true | 取消focus行对应的index

### getFocusRow

**说明**

获取focus行对象

**返回值**

focus行对象

### getFocusRowIndex

**说明**

获取focus行对应的index

**返回值**

focus行对应的index

### getAllRows

**说明**

获取所有行对象

**返回值**

所有行对象

### getRowByIndex

**说明**

根据行号获取行对象

**返回值**

行号对应的行对象

**参数说明**

参数    | 类型      | 是否必须 | 说明
----- | ------- | ---- | ----------------
index | integer | true | 需要获取的行对象对应的index

### getRowIndexByValue

**说明**

根据value值获取行号

**返回值**

查找到的行号

**参数说明**

参数    | 类型     | 是否必须 | 说明
----- | ------ | ---- | --------------
field | stirng | true | value值对应的field
value | string | true | value值

### getChildRowIndex

**说明**

树表展示下根据row对象获取此row下所有子元素的rowIndex

**返回值**

查找到的行号

**参数说明**

参数  | 类型     | 是否必须 | 说明
--- | ------ | ---- | -----------
row | object | true | grid中的row对象

### getColumnByVisibleIndex

**说明**

获取显示的第N列的column对象

**返回值**

查找到的行号

**参数说明**

参数    | 类型      | 是否必须 | 说明
----- | ------- | ---- | ----------------
index | integer | true | 需要查找的列在所有显示列中的序号

### setRenderType

**说明**

设置某列的renderType属性

**返回值**

无

**参数说明**

参数         | 类型       | 是否必须 | 说明
---------- | -------- | ---- | -------------------------
field      | string   | true | 设置renderType属性数据列对应的field
renderType | function | true | 新的renderType

### setShowHeader

**说明**

设置是否显示表头

**返回值**

无

**参数说明**

参数         | 类型      | 是否必须 | 说明
---------- | ------- | ---- | -----------------------------
showHeader | boolean | true | true表示设置为显示表头，false表示设置为不显示表头

### setColumnPrecision

**说明**

设置数据列的精度

**返回值**

无

**参数说明**

参数    | 类型     | 是否必须 | 说明
----- | ------ | ---- | ----------------
field | string | true | 需要设置的数据列对应的field

### setMultiSelect

**说明**

设置是否显示复选框

**返回值**

无

**参数说明**

参数          | 类型      | 是否必须 | 说明
----------- | ------- | ---- | -------------------------
multiSelect | boolean | true | true表示显示复选框，false表示不显示复选框

### setShowNumCol

**说明**

设置是否显示数字列

**返回值**

无

**参数说明**

参数         | 类型      | 是否必须 | 说明
---------- | ------- | ---- | -------------------------
showNumCol | boolean | true | true表示显示数字列，false表示不显示数字列

### setEditType

**说明**

设置某列的editType属性

**返回值**

无

**参数说明**

参数       | 类型       | 是否必须 | 说明
-------- | -------- | ---- | -----------------------
field    | string   | true | 设置editType属性数据列对应的field
editType | function | true | 新的editType

### setEditable

**说明**

设置是否支持编辑功能

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | ---------------------------
editable | boolean | true | true表示支持编辑功能，false表示不支持编辑功能

### setGridEditType

**说明**

设置编辑方式

**返回值**

无

**参数说明**

参数          | 类型     | 是否必须 | 说明
----------- | ------ | ---- | ---------------------------------------
newEditType | string | true | default表示在数据行上进行编辑，form表示在单独的form区域进行编辑

### setGridEditTypeAndEditRow

**说明**

设置编辑方式同时出发对应单元格的编辑

**返回值**

无

**参数说明**

参数          | 类型      | 是否必须 | 说明
----------- | ------- | ---- | ---------------------------------------
newEditType | string  | true | default表示在数据行上进行编辑，form表示在单独的form区域进行编辑
rowIndex    | integer | true | 单元格对应的行号
colIndex    | integer | true | 单元格对应的列号

### expandNode

**说明**

树表形式下通过value展开某个节点

**返回值**

无

**参数说明**

参数       | 类型     | 是否必须 | 说明
-------- | ------ | ---- | --------------------
keyValue | string | true | 需要展开节点的keyField对应的数值

### expandNodeByIndex

**说明**

树表形式下通过index展开某个节点

**返回值**

无

**参数说明**

参数       | 类型      | 是否必须 | 说明
-------- | ------- | ---- | ------------
rowIndex | integer | true | 需要展开节点的index

