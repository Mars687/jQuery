# jQuery
jQuery learning note

toggleClass() 对设置或移除被选元素的一个或多个类进行切换。

该方法检查每个元素中指定的类。如果不存在则添加类，如果已设置则删除之。这就是所谓的切换效果。
不过，通过使用 "switch" 参数，您能够规定只删除或只添加类。
语法：
$(selector).toggleClass(class,switch)

class	：必需。规定添加或移除 class 的指定元素。如需规定若干 class，使用空格来分隔类名。
switch	可选。布尔值。规定是否添加（true）或移除（false）class。
