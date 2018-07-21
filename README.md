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
