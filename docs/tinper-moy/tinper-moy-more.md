# 附录
## 什么是 Knockout? 
 Knockout是一款很优秀的JavaScript库，它可以帮助你仅使用一个清晰整洁的底层数据模型（data model）即可创建一个富文本且具有良好的显示和编辑功能的用户界面。任何时候你的局部UI内容需要自动更新（比如：依赖于用户行为的改变或者外部的数据源发生变化），KO都可以很简单的帮你实现，并且非常易于维护。
## 有哪些优点?
KO重要特性：
优雅的依赖跟踪-任何时候当数据源模型发生变化时，它都能够自动的更新你UI的指定内容。

声明式绑定-它通过简单浅显的方式将你的UI与数据源模型进行绑定，你可以使用任意嵌套的结构模版来组建一个复杂的动态界面。

良好的可扩展性-通过简单的几行代码就可以实现一个自定义行为作为新的声明进行绑定。

其他优点：
纯JavaScript库-兼容任何服务器和客户端技术。

可以很好的应用到已有的应用程序中-而不需要程序主要架构发生变化。

简洁-采用Gzip压缩之后只要13K。

兼容任何主流浏览器-(IE 6+, Firefox 2+, Chrome, Safari, 及其他)

一套全面完整的规范（采用行为驱动开发）-这意味着在新的浏览器或平台中也能够很容易验证通过。

开发人员如果熟悉Ruby on Rails，Asp.net MVC 或其它MVC技术可能会发现它是一个带有声明式语法的MVC实时form。换句话说，你可以把KO当成通过编辑JSON数据来制作UI用户界面的一种方式… 不管它为你做什么。

## 如何使用?
最快速、最有趣的方式就是通过互动式教学的方式来开始学习，一旦你掌握了最基本的技巧，学习了每个在线实例，你就可以在你的项目中一展身手了。

## data-bind声明式绑定
- bisible
  ` <div id="myview" data-bind="visible : isVisible"> visible bind </div>`
- text 
  ` <div id="myview" data-bind="text : name">`
- html
  ` <div id="myview" data-bind="html : htmlContent">`
- css 
  ` <div id="myview" data-bind="css : {redbg : testValue() < 0}">`
- attr
  ` <div id="myview" data-bind="attr : {title : titleName}">`
- click
  ` <div data-bind="text : clickCount">`
- foreach
  ` <tbody data-bind="foreach: people"><tr><td data-bind="text: firstName"></td> <td data-bind="text: lastName"></td></tr></tbody>`
- ` js 部分: ko.applyBindings({         people: [             { firstName: 'Bert', lastName: 'Bertington' },             { firstName: 'Charles', lastName: 'Charlesforth' },             { firstName: 'Denise', lastName: 'Dentiste' }         ]     });`   
- 增加节点

```
<script type="text/javascript" src="knockout-2.2.0.js"></script>

 <h4>People</h4> 
 <ul data-bind="foreach: people"> 

     <li> 

         Name at position <span data-bind="text: $index"> </span>: 

         <span data-bind="text: name"> </span> 

         Remove 

     </li> 

 </ul> 

 <button data-bind="click: addPerson">Add</button>

 <script type="text/javascript">

     function AppViewModel() {

         var self = this;
self.people = ko.observableArray([
     { name: 'Bert' },
     { name: 'Charles' },
     { name: 'Denise' }
 ]);
 
     self.addPerson = function () {
         self.people.push({ name: "New at " + new Date() });
     };
 
     self.removePerson = function () {
         self.people.remove(this);
     }
 }
 
 ko.applyBindings(new AppViewModel());
  </script>
```



- 如果我们想要输出数组中的所有元素而不是像例一中使用firstName去指定元素的话，我们可以使用$data来进行输出。

    <script type="text/javascript" src="knockout-2.2.0.js"></script>
     <ul data-bind="foreach: months"> 
         The current item is: <b data-bind="text: $data"></b> 
     </li> 
     </ul> 
     <script type="text/javascript"> 
     ko.applyBindings({
         months: ['Jan', 'Feb', 'Mar', 'etc']
     }); 
    </script>    

- 使用$index、$parent等其他的上下文属性
-   <b data-bind="text: name"></b> likes the blog post <b data-bind="text: $parent.blogPostTitle"></b>
- 使用"as"为foreach中的元素定义别名我们可以使用$data来代替数组中的元素，同时我们也可以使用as来为我们要遍历的元素起一个别名。

    <script type="text/javascript" src="knockout-2.2.0.js"></script>
    	<ul data-bind="foreach: { data: categories, as: 'category' }"> 
    		<li> 
                <ul data-bind="foreach: { data: items, as: 'item' }"> 
                     <li> 
                         <span data-bind="text: category.name"></span>: 
                        <span data-bind="text: item"></span> 
                    </li> 
                </ul> 
    		</li> 
    	</ul> 
     <script>

     var viewModel = {
    
         categories: ko.observableArray([
    
             { name: 'Fruit', items: ['Apple', 'Orange', 'Banana'] },
    
             { name: 'Vegetables', items: ['Celery', 'Corn', 'Spinach'] }
    
         ])
    
     };
    
     ko.applyBindings(viewModel); 

 [更多请参考](http://www.aizhengli.com/knockoutjs/)
