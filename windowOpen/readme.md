平稳退化
----
当JS无法被支持，网页应该可以正常的被读取<br />
就像CSS无法加载时，你仍然可以获得所有HTML内容一样，所以不应该因为对href设置了JS函数，就将其设为空值“#”<br />
 
------
分离javascript
----
在文档中使用onclick调用js函数就像用style设置css属性一样，缺乏效率，容易引发问题<br />
更好的方式是用挂钩：class\id，将js于html彻底分离<br />
在外部将一个事件加入html文档：element.event=action<br />
将事件添加到某个带有特定ID属性的元素上：getElementById(id).event=action.<br />
 
---------
向后兼容/性能考虑
----
要让HTML加载完毕后在调用脚本，不然可能因为DOM加载不完全有些函数无法调用，这就用到了：window.onload = name;function name(){...};<br />
测试浏览器是否支持js中的某些方法：<br />
if(!getElementsById||!getElementsByTagName)return false;<br />
意味：如果浏览器不理解XX或YY，则无法继续前进<br />
