# jQuery

## jQuery基础
* $(selector).action()
	* $定义jQuery
	* selector:选择的对象
		* this当前元素
		* "p" 所有P标签
		* "p.test" class为test的p元素
		* "#test" ID为test的元素

* 文档就绪事件:在DOM完全加载之后才进行响应操作
	* $(document).ready(function(){ 执行代码; });
	* $(function(){ 简洁写法; 效果相同; });

* 选择器:
	* 元素选择器：$("p") -> 所有P元素
	* #id选择器：$("#id") -> ID为该ID的元素
	* class选择器：$(".test") -> 任意class为test的元素。因为未指定元素
	* $("*")：所有元素
	* $(this)：当前HTML元素
	* 。。。。。。

* 独立文件使用JQuery函数：<script src="any.js" ></script>

* jQuery事件
	* 事件分类
		* 鼠标事件：click dblclick mouseenter mouseleave
		* 键盘事件：keypress keydown keyup
		* 表单事件：submit change focus blur
		* 文档/窗口事件：load resize scroll unload
	* jQuery事件方法语法：$("p").click(function(){ 执行代码 });
	* 常用的jQuery事件
		* 文档加载完成：$(document).ready();
		* 点击：$("p").click();
		* 双击：$("p").dblclick();
		* 鼠标移动到上面/离开：$("#id").mouseenter();/mouseleave();
		* 鼠标按下、松开：$("#id").mousedown();/mouseup();
		* 模拟光标悬停事件：$("#id").hover(function(){ 悬停； }, function(){ 离开；});
		* 获得焦点：$("p").focus();
		* 失去焦点：$("p").blur();

## jQuery效果
* 隐藏显示：$("#id").hide(); 
	* $(selector).hide(speed,callback);
	* 可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。
	* 可选的 callback 参数是隐藏或显示完成后所执行的函数名称。
	* $("#id").toggle(); 隐藏展示的，展示隐藏的

* 淡入淡出：fade
	* 淡入：$(selector).fadeIn(speed, callback);
		* $(selector).fadeIn(1000);
		* $(selector).fadeIn("slow");
	* 淡出：$(".test").fadeOut(speed, callback);
	* 自动淡入淡出：$(selector).fadeToggle();
	* 渐变：$("*").fadeTo(speed, opacity, callback);

[当前进度](http://www.runoob.com/jquery/jquery-slide.html)
