# [jQuery](http://www.runoob.com/jquery/jquery-tutorial.html)

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

* 滑动：slide
	* $(selector).slideDown();/slideUp();/slideToggle();

* 动画：
	* $(selector).animate({params}, speed, callback);
	* 必需的 params 参数定义形成动画的 CSS 属性。
	* 默认情况下，所有HTML元素都有一个静态位置，且无法移动。如需对位置进行操作，要记得首先把元素的 CSS position 属性设置为 relative、fixed 或 absolute！
	* 可同时操作多个属性
	* 使用相对值：css属性例如：height: '+=150px';
	* 使用预定义值：例如 height: 'toggle';   show/hidden
	* 队列功能：{ 多个animation顺序执行; }

* 停止动画：
	* $(selector).stop(stopAll, goToEnd);
	* 可选的 stopAll 参数规定是否应该清除动画队列。默认是false，即仅停止活动的动画，允许任何排入队列的动画向后执行。
	* 可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false
* jQuery callback
	* Callback 函数在当前动画 100% 完成之后执行。
	* $("p").hide("slow",function(){ });
* jQuery 链式语法 chain
	* 通过 jQuery，可以把动作/方法链接在一起。
	* $("#p1").css("color","red").slideUp(2000).slideDown(2000);

## jQuery HTML
* jQuery获取属性和内容
	* 获得内容
		* $("#test").text();
		* $("#test").html();
		* $("#test").val(); 设置或返回表单字段值
	* 获取属性：
		* $("#test").attr("href");

* jQuery设置内容和属性
	* 同上
	* $("#test").text("你好");
	* 回调函数：$("#test").text(function(){ 执行代码; });
	* 设置属性：$("#test").attr("href", "http://www.baidu.com");
	* 设置属性回调函数：$("#test").attr("href", function(){ 执行代码; });
* jQuery添加元素
	* 在被选元素的结尾插入内容：$("#test").append("内容");
	* 在被选元素开头插入内容：$("#test").prepend("插入开头")；
	* append、prepend添加新元素实例
		* html创建：var txt = "<p>文本</p>";
		* jQuery创建：var txt = $("<p></p>").text("文本");
		* DOM创建：var txt = document.createElement("p"); txt.innserHtml="文本";
	* after、before：$("#id").after("文本");/before("文本");

* jQuery删除元素
	* $(selector).remove();删除元素及所有子元素
	* $(selector).empty();删除子元素
	* $(selector).remove(".italic");删除class名为italic的所有元素

* jQuery操作CSS
	* 属性存储在CSS样式表内
	* 添加class属性：
		* $("h1, h2, p").addClass("blue, important");
		* 可以向单个元素添加单个属性
		* 可以向单个元素添加多个属性，以此类推
	* 移除class属性
		* $(selector).removeClass("blue");
	* 反转属性：
		* $(selector).toggleClass("blue");

* jQuery css()
	* css() 方法设置或返回被选元素的一个或多个样式属性。
	* 获取属性 css(propertyName);
		* $("p").css("backgroud-color")
	* 设置属性 css(propertyName, propertyValue);
		* $("p").css("background-color", "yellow");
	* 设置多个属性：
		* $("p").css({"background-color":"yellow", "font-size":"200%"});

* jQuery尺寸
	* width();元素的宽度
	* height(); 元素的高度
	* innerWidth(); 包含内边距的宽度 + padding*2
	* innerHeight(); 包含内边距的高度 + padding*2
	* outerWidth/Height(); 包含内边距和边框的宽度、高度 + padding*2 + border*2

* jQuery遍历
	* 从被选（当前的）元素开始，轻松地在家族树中向上移动（祖先），向下移动（子孙），水平移动（同胞）。这种移动被称为对 DOM 进行遍历。
	* 遍历方法中最大的种类是树遍历（tree-traversal）。

* jQuery祖先
	* parent(); 该元素的直接父
	* parents(); 该元素所有祖先
	* parents("类型"); 该元素所有祖先的该类型的元素
	* $("span").parentsUntil("div"); div和span之间的所有元素

* jQuery子类
	* $("div").children(); div元素的所有直接子类
	* $("div").children("p.1"); div元素的所有子类中是P类型且class为1的元素
	* $("div").find("*"); 查找div所有后代子元素
	* $("div").find("span"); 查找div子类中所有span类型
* jQuery同胞
	* $("h2").sublings(); 该元素所有同胞。同级别元素
	* $("h2").sublings("p"); 该元素同级的所有p类型元素
	* next(); -> $("h2").next(); 被选元素的下一个元素 同级
	* nextAll(); 被选元素同级的从这个开始到结束的所有子元素
	* $("h2").nextUntil("h6"); 从当前元素直到某元素之间的元素
	* pre与next方向相反，其它相同。prev(); prevAll(); prevUntil();
* jQuery过滤
	* $("div p").first(); 首个div的第一个p
	* $("div p").last(); 首个div最后一个P
	* $("div").eq(1); 带有指定索引号的元素 -> <p>http://www.runoob.com (index 1)。</p>
	* $("p").filter(".url"); 该类型元素的class是url的所有元素

## jQuery与AJAX
* 略

## jQuery其它
* 框架兼容
	* $.noConflict(); 然后直接使用jQuery调用对应方法。
	``` js
	$.noConflict();
		jQuery(document).ready(function(){
 		 jQuery("button").click(function(){
   		 jQuery("p").text("jQuery 仍然在工作!");
  		});
	});
	```
	* var jq = $.noConflict();变量代替$符号
	* jQuery(document).ready(function($){ 在函数中传递jQuery对象为$符号
* JSONP
	* 原生:
		* <script type="text/javascript" src="http://www.runoob.com/try/ajax/jsonp.php?jsoncallback=callbackFunction"></script> 实现该方法
		* function callbackFunction(result, methodName){}; 方法内处理
		* 获取元素插入处理道德数据
	* jQuery处理：
		* script标签内部
		* $.getJSON("http://www.runoob.com/try/ajax/jsonp.php?jsoncallback=?", function(data) {}; 处理数据返回

## jQuery补充
* 选择器
	* $("tr:even")	偶数<tr>元素
	* $("tr:odd") 技术<tr>元素
* 事件方法：
	* bind();
		* $("p").bind("click",function(){ 执行方法; };
* jQuery与ajax
	```js
	$("button").click(function(){
    	$.ajax({url:"demo_test.txt",success:function(result){
       		 $("#div1").html(result);
    	}});
	});
	```
