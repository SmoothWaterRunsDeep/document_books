**1.jq的两种入口函数的写法**

​	$(document).ready(function(){
​	    console.log('这是jq入口函数的第一种写法')
​	})
​	
​	$(function(){
​	    console.log('这是jq入口函数的第二种写法')
​	})



**2.js与jq之间的区别**

	js的入口函数执行要比jq的入口函数执行的晚一些。
	jq的入口函数会等待页面的加载完成才会执行，但是不会等待图片的加载完毕。
	js的入口函数会等待网页和图片的全部加载完毕才会开始执行。
	
	jq对象无法调用DOM对象的方法
	DOM无法调用jq对象的方法，因为两个是不同对象
	DOM对象无法调用jq对象的方法，需要把DOM对象转化成jq对象 
	
	用$把DOM对象包起来就可以让DOM对象变成jq对象
	把DOM对象从jq对象中取出来就可以把jq对象变成DOM对象
	eg：
		var lis = $('li');
		lis[0].style.background = 'red'
		这是通过数列的下标或索引将DOM对象从jq对象中提取出来的



**3.$的详细用法**

	$其实是一个函数，后面使用的时候需要跟上（），$()中传递的参数不同，功能也不一样。
		1.参数是function，入口函数
			$(function(){
	           console.log('入口函数') 
			});
		2.参数如果是DOM对象，把DOM对象转化成jq对象
			$(domobj)
	    $(document).ready(function(){
	       console.log('入口函数') 
	    });
		3.参数是一个字符串,用来找对象
			$('div')、 $('.current')



**4、jQuery如何用选择器**

	css（name, value）
	name:样式名   value：样式值
	$('#four').css('background',red);
	
	交集与并集
	
		交集：$("#four,.green").css("backgroundColor","pink");
		并集：$("li.green").css("backgroundColor","yellow")
![1538920757012](/home/dell/.config/Typora/typora-user-images/1538920757012.png)

![1538920792972](/home/dell/.config/Typora/typora-user-images/1538920792972.png)



****

**5、mouseover与mouseenter的区别**
	mouseover：
		不论鼠标指针是否穿过被选元素或其子元素，都会触发mouseover事件。
	mouseenter：
		只有在鼠标指针经过被选元素时，才会触发mouseenter事件
	
	如果设置了mouseover事件的元素的外层还有一个父级元素，那么mouseover就会被触发两次，与mouseenter比较起来就存在了误差，以及较低的效率。