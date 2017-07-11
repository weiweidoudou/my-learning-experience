$("选择器")   用这种方法获得jquery对象，括号里面一定加“”。否则会报错

在引入jquery库的前面引入了其他的库如prototype库，可以在js代码中调用jQuery.noConflict()函数来将变量$的控制权移交给其他JavaScript库，  若想为jQuery定义一个快捷方式，可以使var $j=jQuery.noConflict();   则$j为jQuery的快捷方式。而$为其他库的快捷方式    还有两种方法。详情见《锋利的jQuery》  16面
在引入jQuery库的后面引入了其他的库如prototype库，那么就可以直接使用jQuery来做一些jQuery的工作。同时使用$()方法作为其他库的快捷方式

jQuery 代码最好写在$(function(){

});   里面


若发现js代码无误。而效果又出不来，看看是否为将代码写在window.onload=function(){};里面      切记切记！

基本过滤选择器中的：eq(index)  :gt(index)   :lt(index)   index都是从0开始
子元素过滤选择器中的  :nth-child(index)     index都是从1开始的




选择器中的空格不容忽视。多写一个少写一个会有很大的差别


filter（expr）与find()

filter(expr)筛选出与指定表达式匹配的元素集合，其中expr可以使多个选择器的集合，用，分隔，如$('ul li').filter(":contains('佳能'),:contains('尼康'),:contains('奥林巴斯')")

而find()会在子元素中寻找匹配元素


css（）方法获取的高度值与样式的设置有关，可能会得到“auto”，也可能不得到“10px"之类的字符串，而height（）方法获取的高度值是元素在页面中的实际高度，与样式的设置无关，并且不带单位


js中调用对象的属性直接用   element.href    element.title;


event.pageX  不带单位   注意注意！！！




停止事件的冒泡， event.stopPropagation()
取消单链接跳转，取消表单提交 even.preventDefault()
上面两个可以用return false

$(":checkbox[name='items']").attr("checked",false); //有效果
$(":checkbox[name='items']").attr("checked","false"); //无效果

attr("属性名","属性值")；如果属性值是数字或者boolean类型的就不用加引号


为select设置multiple="multiple"可以改变下拉框的默认样式


//					$("textarea").animate({"scrollTop":"+=50"},"slow");//有效果
//				
//					$("textarea").css("scrollTop",50);//没变化，动都不动==

//					$("textarea").css("scrollTop","+=50");//没变化，动都不动==

					$("textarea").scrollTop(50);//有效果
因为scrollTop是属性，不能用css（）操作，只能通过设置scrollTop属性或者scrollTop（）设置

animated（{property1:"value1",property2:"value2",……},speed,callback）中第一个参数是对象，对象里面设置的是属性。


$(this).addClass("selected")
					.find("input").attr("checked",true)
					.end()
					.siblings().removeClass("selected");
需要重新返回到$(this)对象，就可以使用end()方法

input中修改默认文字颜色   		<input type="text" placeholder="输入商品名称" />
:-moz-placeholder { /* Mozilla Firefox 4 to 18 */
    color: #000; opacity:1; 
}

::-moz-placeholder { /* Mozilla Firefox 19+ */
    color: #000;opacity:1;
}

input:-ms-input-placeholder{
    color: #000;opacity:1;
}

input::-webkit-input-placeholder{
    color: #000;opacity:1;
}


若想要获取到一个元素的索引值
用index()方法   例如var index=$父元素.index(子元素)