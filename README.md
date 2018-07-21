# jQuery learning note

toggleClass() 对设置或移除被选元素的一个或多个类进行切换。

该方法检查每个元素中指定的类。如果不存在则添加类，如果已设置则删除之。这就是所谓的切换效果。
不过，通过使用 "switch" 参数，您能够规定只删除或只添加类。
语法：
$(selector).toggleClass(class,switch)

class	：必需。规定添加或移除 class 的指定元素。如需规定若干 class，使用空格来分隔类名。
switch	可选。布尔值。规定是否添加（true）或移除（false）class。


.html()方法 

获取集合中第一个匹配元素的HTML内容 或 设置每一个匹配元素的html内容，具体有3种用法：

.html() 不传入值，就是获取集合中第一个匹配元素的HTML内容
.html( htmlString )  设置每一个匹配元素的html内容
.html( function(index, oldhtml) ) 用来返回设置HTML内容的一个函数
注意事项：

.html()方法内部使用的是DOM的innerHTML属性来处理的，所以在设置与获取上需要注意的一个最重要的问题，这个操作是针对整个HTML内容（不仅仅只是文本内容）


.text()方法

得到匹配元素集合中每个元素的文本内容结合，包括他们的后代，或设置匹配元素集合中每个元素的文本内容为指定的文本内容。，具体有3种用法：

.text() 得到匹配元素集合中每个元素的合并文本，包括他们的后代
.text( textString ) 用于设置匹配元素内容的文本
.text( function(index, text) ) 用来返回设置文本内容的一个函数
注意事项：

.text()结果返回一个字符串，包含所有匹配元素的合并文本
.html与.text的异同:

.html与.text的方法操作是一样，只是在具体针对处理对象不同
.html处理的是元素内容，.text处理的是文本内容
.html只能使用在HTML文档中，.text 在XML 和 HTML 文档中都能使用
如果处理的对象只有一个子文本节点，那么html处理的结果与text是一样的
火狐不支持innerText属性，用了类似的textContent属性，.text()方法综合了2个属性的支持，所以可以兼容所有浏览器


.val()方法
.val()方法主要是用于处理表单元素的值，比如 input, select 和 textarea。

.val()无参数，获取匹配的元素集合中第一个元素的当前值
.val( value )，设置匹配的元素集合中每个元素的值
.val( function ) ，一个用来返回设置值的函数
 注意事项：

通过.val()处理select元素， 当没有选择项被选中，它返回null
.val()方法多用来设置表单的字段的值
如果select元素有multiple（多选）属性，并且至少一个选择项被选中， .val()方法返回一个数组，这个数组包含每个选中选择项的值
 

.html(),.text()和.val()的差异总结：  

.html(),.text(),.val()三种方法都是用来读取选定元素的内容；只不过.html()是用来读取元素的html内容（包括html标签），.text()用来读取元素的纯文本内容，包括其后代元素，.val()是用来读取表单元素的"value"值。其中.html()和.text()方法不能使用在表单元素上,而.val()只能使用在表单元素上；另外.html()方法使用在多个元素上时，只读取第一个元素；.val()方法和.html()相同，如果其应用在多个元素上时，只能读取第一个表单元素的"value"值，但是.text()和他们不一样，如果.text()应用在多个元素上时，将会读取所有选中元素的文本内容。
.html(htmlString),.text(textString)和.val(value)三种方法都是用来替换选中元素的内容，如果三个方法同时运用在多个元素上时，那么将会替换所有选中元素的内容。
.html(),.text(),.val()都可以使用回调函数的返回值来动态的改变多个元素的内容。

jQuery remove() 方法删除被选元素及其子元素。
jQuery empty() 方法删除被选元素的子元素。

当鼠标指针穿过（进入）被选元素时，会发生 mouseenter 事件。
mouseenter() 方法触发 mouseenter 事件，或添加当发生 mouseenter 事件时运行的函数。

注意：与 mouseover 事件不同，mouseenter 事件只有在鼠标指针进入被选元素时被触发，mouseover 事件在鼠标指针进入任意子元素时也会被触发。

event.type：获取事件的类型

触发元素的事件类型

$("a").click(function(event) {
  alert(event.type); // "click"事件
});
event.pageX 和 event.pageY：获取鼠标当前相对于页面的坐标

通过这2个属性，可以确定元素在当前页面的坐标值，鼠标相对于文档的左边缘的位置（左边）与 （顶边）的距离，简单来说是从页面左上角开始,即是以页面为参考点,不随滑动条移动而变化

event.preventDefault() 方法：阻止默认行为

这个用的特别多，在执行这个方法后，如果点击一个链接（a标签），浏览器不会跳转到新的 URL 去了。我们可以用 event.isDefaultPrevented() 来确定这个方法是否(在那个事件对象上)被调用过了

event.stopPropagation() 方法：阻止事件冒泡

事件是可以冒泡的，为防止事件冒泡到DOM树上，也就是不触发的任何前辈元素上的事件处理函数

event.which：获取在鼠标单击时，单击的是鼠标的哪个键

event.which 将 event.keyCode 和 event.charCode 标准化了。event.which也将正常化的按钮按下(mousedown 和 mouseupevents)，左键报告1，中间键报告2，右键报告3

event.currentTarget : 在事件冒泡过程中的当前DOM元素

冒泡前的当前触发事件的DOM对象, 等同于this.

this和event.target的区别：

js中事件是会冒泡的，所以this是可以变化的，但event.target不会变化，它永远是直接接受事件的目标DOM元素；

.this和event.target都是dom对象

如果要使用jquey中的方法可以将他们转换为jquery对象。比如this和$(this)的使用、event.target和$(event.target)的使用；
