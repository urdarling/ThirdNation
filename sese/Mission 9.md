# Mission 9

### Http聊天室

##### http简介

问：什么是HTTP?
答：HTTP是一个客户端和服务器端请求和响应的标准TCP。其实建立在TCP之上的。

当我们打开百度网页时，是这样的：

    https://www.baidu.com

多了个S，其实S表示TLS、SSL。在这里不做解释，因此HTTP的技术基石如图所示：

那HTTP协议呢？HTTP协议（HyperText Transfer Protocol）,即超文本传输协议是用于服务器传输到客户端浏览器的传输协议。Web上，服务器和客户端利用HTTP协议进行通信会话。有OOP思想的得出结论：其会话的结构是一个简单的请求/响应序列，即浏览器发出请求和服务器做出响应。
二、深入理解技术基石和工作流程

既然HTTP是基于传输层的TCP协议，而TCP协议是面向连接的端到端的协议。因此，使用HTTP协议传输前，首先建立TCP连接，就是因此在谈的TCP链接过程的“三次握手”。如图

在Web上，HTTP协议使用TCP协议而不是UDP协议的原因在于一个网页必须传送很多数据，而且保证其完整性。TCP协议提供传输控制，按顺序组织数据和错误纠正的一系列功能。

一次HTTP操作称为一个事务，其工作过程可分为四步：

    1、客户端与服务器需要建立连接。（比如某个超级链接，HTTP就开始了。）
    
    2、建立连接后，发送请求。
    
    3、服务器接到请求后，响应其响应信息。
    
    4、客户端接收服务器所返回的信息通过浏览器显示在用户的显示屏上，然后客户机与服务器断开连接。

建立连接，其实建立在TCP连接基础之上。图解核心工作过程（即省去连接过程）如下：
三、详解工作过程的HTTP报文

HTTP报文由从客户机到服务器的请求和从服务器到客户机的响应构成。

一、请求报文格式如下：

    请求行
    
    通用信息头
    
    请求头
    
    实体头
    
    （空行）
    
    报文主体

如图，请求我博客一篇文章时发送的报文内容：

对于其中请求报文详解:

    1、请求行
    
    方法字段 + URL + Http协议版本
    
    2、通用信息头
    
    Cache-Control头域：指定请求和响应遵循的缓存机制。
    
    keep-alive 是其连接持续有效【在下面百度的例子，会得到验证】
    
    3、请求头
    
    Host头域，脑补吧
    
    Referer头域：允许客户端指定请求URL的资源地址。
    
    User-Agent头域：请求用户信息。【可以看出一些客户端浏览器的内核信息】
    
    4、报文主体
    
    如图中的 “ p=278 ”一般来说，请求主体少不了请求参数。

二、应答报文格式如下：

    状态行
    
    通用信息头
    
    响应头
    
    实体头
    
    （空行）
    
    报文主体

如图，就是这篇博客响应的内容:

对其中响应报文详解：

    1、状态行
    
    HTTP协议版本 + 状态码 + 状态代码的文本描述
    
    【比如这里，200 代表请求成功】
    
    2、通用信息头
    
    keep-alive 是其连接持续有效【在下面百度的例子，会得到验证】
    
    Date头域：时间描述
    
    3、响应头
    
    Server头：处理请求的原始服务器的软件信息。
    
    4、实体头
    
    Content-Type头：便是接收方实体的介质类型。（这也表示了你的报文主体是什么。）
    
    （空行）
    
    5、报文主体
    
    这里就是HTML响应页面了，在截图tab页中的response中可查看。

一次简单的请求/响应就完成了。

##### http原理

客户机与服务器建立连接后，发送一个请求给服务器，请求格式为：统一资源标识符、协议版本号。服务器收到请求的信息（包括请求行，请求头，请求体）。服务器接收到请求后，给予相应的响应信息，格式为一个状态行（包括响应行，响应头，响应体）。

在internet上，http通讯通常发生在TCP/IP连接之上。缺省端口是TCP的80端口。

基于HTTP协议的客户/服务器模式的信息交换过程，分为四个过程：建立连接、发送请求信息、发送响应信息、关闭连接。

服务器可能同时接受多个请求，这时就会产生多个sessoin，每个session分别处理各自的请求。


HTTP的工作过程
一次HTTP操作称为一个事务，其工作整个过程如下：
1）、地址解析
  如用客户端浏览器请求这个页面：http://localhost.com:8080/index.htm

     从中分解出协议名、主机名、端口、对象路径等部分，对于我们的这个地址，解析得到的结果如下：
     协议名：http
     主机名：localhost.com
     端口：8080
     对象路径：/index.html
    
      在这一步，需要域名系统DNS解析域名localhost.com,得主机的IP地址。


2）、封装HTTP请求数据包
  把以上部分结合本机自己的信息，封装成一个HTTP请求数据包


3）封装成TCP包，建立TCP连接（TCP的三次握手）
       在HTTP工作开始之前，客户机（Web浏览器）首先要通过网络与服务器建立连接，该连接是通过TCP来完成的，该协议与IP协议共同构建Internet，即著名的TCP/IP协议族，因此Internet又被称作是TCP/IP网络。HTTP是比TCP更高层次的应用层协议，根据规则，只有低层协议建立之后才能，才能进行更层协议的连接，因此，首先要建立TCP连接，一般TCP连接的端口号是80。这里是8080端口


4）客户机发送请求命令
       建立连接后，客户机发送一个请求给服务器，请求方式的格式为：统一资源标识符（URL）、协议版本号，后边是MIME信息包括请求修饰符、客户机信息和可内容。

5）服务器响应
   服务器接到请求后，给予相应的响应信息，其格式为一个状态行，包括信息的协议版本号、一个成功或错误的代码，后边是MIME信息包括服务器信息、实体信息和可能的内容。
        实体消息是服务器向浏览器发送头信息后，它会发送一个空白行来表示头信息的发送到此为结束，接着，它就以Content-Type应答头信息所描述的格式发送用户所请求的实际数据


6）服务器关闭TCP连接
     一般情况下，一旦Web服务器向浏览器发送了请求数据，它就要关闭TCP连接，然后如果浏览器或者服务器在其头信息加入了这行代码
    Connection:keep-alive
   TCP连接在发送后将仍然保持打开状态，于是，浏览器可以继续通过相同的连接发送请求。保持连接节省了为每个请求建立新连接所需的时间，还节约了网络带宽。



服务器将响应信息传给客户端，响应体中的内容可能是一个html页面，也可能是一张图片，通过输入流将其读出，并写回到显示器上。

#### 聊天室搭建

▍实现过程（Windows系统）

1、在nodeJS中文网下载nodeJS客户端并安装；

2、在桌面（未知可自选）创建一个项目文件夹用于存放相关文件；

3、打开新建的文件夹，创建chatRoom.html文件和server.js文件；

4、打开命令行窗口，找到这个文件夹后，输入【npm i socket.io】，此时将在该文件夹中生成了一个新的文件夹，这是刚刚下载的socket.io相关依赖包；

5、将代码补充到chatRoom.html文件和server.js文件中；

6、打开命令行窗口，找到该项目文件夹后，输入【node server.js】并【Enter】。

7、保持窗口在运行状态，不要关闭！！！

▍有待完善的地方

1、没有实现动态的分配身份；

2、界面可再优化；

3、前台向后台发送中文姓名时会出现乱码（找了两天资料都没有搞定，跪求大佬指教）。

> server.js
>
> ```js
> // 引入http标准模块,CommonJS模块
> const http = require("http");
> const fs = require("fs");
> const ws = require("socket.io");
> // 当前在线人数
> let count = 0;
> // 总访客人数
> let totalCount = 0;
>  
> // 创建一个web服务器
> const server = http.createServer(function(request, response) {
> 	response.writeHead(200, {
> 		"Content-Type": "text/html;charset=UTF-8"
> 	});
> 	// 可发送文本
> 	// response.end("hello world");
>  
> 	// 可自动解析html
> 	// response.end("<h1>我是标题2</h1>");
>  
> 	// 读取文件
> 	const html = fs.readFileSync("index.html");
> 	response.end(html);
>  
> });
>  
> // 基于当前web服务器开启socket实例
> const io = ws(server);
>  
> // 检测连接事件
> io.on("connection", function(socket) {
>  
> 	// console.log("当前有用户连接");
> 	count++;
> 	totalCount++;
> 	// console.log("count:" + count);
>  
> 	let name = '';
>  
> 	// 给公众发送上线信息
> 	//	socket.broadcast.emit("connection", {
> 	//		count: count,
> 	//		id: count
> 	//	});
>  
> 	// 给自己发送上线信息
> 	//	socket.emit("connection", {
> 	//		count: count,
> 	//		id: totalCount
> 	//	});
>  
> 	// 加入群聊
> 	socket.on("join", function(message) {
> 		console.log(message);
> 		name = message.name;
> 		// console.log(name + "加入了群聊");
> 		socket.broadcast.emit("joinNoticeOther", {
> 			name: name,
> 			action: "加入了群聊",
> 			count: count
> 		});
> 		socket.emit("joinNoticeSelf", {
> 			count: count,
> 			id: totalCount
> 		});
> 	});
>  
> 	// 接收客户端所发送的信息
> 	socket.on("message", function(message) {
> 		console.log(message);
> 		// 向所有客户端广播发布的消息
> 		io.emit("message", message);
> 	});
>  
> 	//	 监听到连接断开
> 	socket.on("disconnect", function() {
> 		count--;
> 		// console.log(name + "离开了群聊")
> 		io.emit("disconnection", {
> 			count: count,
> 			name: name
> 		});
> 	});
>  
> });
>  
> // 服务器监听端口
> server.listen(3000);
> console.log('Server has started.\n')
> 
> ```
>
> chatRoom.html
>
> ```js
> <!DOCTYPE html>
> <html>
>  
> <head>
> 	<meta charset="UTF-8">
> 	<title>蜗牛先生的聊天室</title>
> 	<style>
> 		* {
> 			margin: 0;
> 			padding: 0;
> 		}
>  
> 		html {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			width: 100%;
> 			height: 100%;
> 			overflow: hidden;
> 			background-color: #d4f0fc;
> 			background-image: url(http://tool.uixsj.cn/qchan/uploads/2018/08/traffic_a_lot_of_cars_driving_across_the_golden_gate_bridge_free_stock_photos_picjumbo_HNCK2899_2210x1474.jpg);
> 			background-size: 100% 100%;
> 		}
>  
> 		.chatroom {
> 			display: flex;
> 			width: 1000px;
> 			height: 700px;
> 			border-radius: 20px;
> 			overflow: hidden;
> 		}
>  
> 		.left {
> 			position: relative;
> 			display: flex;
> 			flex-direction: column;
> 			align-content: center;
> 			width: 30%;
> 			height: 100%;
> 			background-color: #478291;
> 		}
>  
> 		.icon-container {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			margin-top: 40px;
> 			height: 30%;
> 		}
>  
> 		.icon-container img {
> 			border: 10px solid #333;
> 			width: 150px;
> 			height: 150px;
> 			object-fit: cover;
> 			border-radius: 50%;
> 		}
>  
> 		.icon-container img:hover {
> 			animation: rotate 2s linear infinite forwards;
> 		}
>  
> 		@keyframes rotate {
> 			from {
> 				transform: rotate(0);
> 			}
>  
> 			to {
> 				transform: rotate(360deg);
> 			}
> 		}
>  
> 		.self-container {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			height: 15%;
> 			line-height: 60px;
> 			font-size: 25px;
> 			font-weight: 700;
> 			color: #cadeea;
> 		}
>  
> 		.function-container {
> 			display: flex;
> 			justify-content: flex-start;
> 			align-items: flex-start;
> 			flex-wrap: wrap;
> 			padding: 0 30px;
> 			color: #617c8f;
> 		}
>  
> 		.function-item {
> 			margin: 5px;
> 			border: 3px solid #333;
> 			padding: 5px 10px;
> 			background: #fff;
> 			font-size: 14px;
> 		}
>  
> 		.note-help {
> 			position: absolute;
> 			bottom: 20px;
> 			padding: 0 30px;
> 			font-size: 12px;
> 			color: #9cadad;
> 			text-align: center;
> 		}
>  
> 		.right {
> 			width: 70%;
> 			height: 100%;
> 			background-color: #eee;
> 		}
>  
> 		.head {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			height: 10%;
> 			width: 100%;
> 			background-color: white;
> 			font-size: 22px;
> 			font-weight: bold;
> 		}
>  
> 		.chat-container {
> 			height: 80%;
> 			overflow-y: scroll;
> 			box-sizing: border-box;
> 		}
>  
> 		.speaker-name {
> 			padding: 5px 0;
> 			font-size: 12px;
> 			color: #888888;
> 		}
>  
> 		.message-self,
> 		.message-other {
> 			display: flex;
> 			flex-direction: row;
> 			flex-wrap: nowrap;
> 			padding: 10px;
> 			width: 100%;
> 			box-sizing: border-box;
> 		}
>  
> 		.message-self {
> 			justify-content: flex-end;
> 		}
>  
> 		.message-container {
> 			display: flex;
> 			flex-direction: row;
> 			max-width: 80%;
> 		}
>  
> 		.message-self .message-content {
> 			padding-right: 10px;
> 		}
>  
> 		.message-other .message-content {
> 			padding-left: 10px;
> 		}
>  
> 		.message-self .message {
> 			background-color: blue;
> 			color: white;
> 		}
>  
> 		.message-other .message {
> 			background-color: white;
> 			color: black;
> 		}
>  
> 		.message-self .speaker-name {
> 			text-align: right;
> 		}
>  
> 		.message-other .speaker-name {
> 			text-align: left;
> 		}
>  
> 		.message {
> 			border-radius: 10px;
> 			padding: 10px;
> 		}
>  
> 		.message-container .icon img {
> 			width: 40px;
> 			height: 40px;
> 			object-fit: cover;
> 			border-radius: 50%;
> 		}
>  
> 		.message-table {
> 			border-collapse: collapse;
> 			border: 2px dashed #aaa;
> 		}
>  
> 		.message-table-th {
> 			border-bottom: 2px dashed #aaa;
> 			padding: 5px 10px;
> 		}
>  
> 		.message-table-td {
> 			padding: 5px 10px;
> 		}
>  
> 		.notify-container {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			width: 100%;
> 			height: 50px;
> 		}
>  
> 		.notify {
> 			border-radius: 10px;
> 			padding: 5px 10px;
> 			background-color: #ddd;
> 			opacity: 0.9;
> 			font-size: 12px;
> 			color: white;
> 		}
>  
> 		.notify-name {
> 			color: blue;
> 		}
>  
> 		.input-container {
> 			display: flex;
> 			flex-direction: row;
> 			justify-content: space-between;
> 			width: 100%;
> 			height: 10%;
> 			background-color: blue;
> 			font-size: 18px;
> 		}
>  
> 		.input-content {
> 			position: relative;
> 			width: 85%;
> 			background-color: white;
> 		}
>  
> 		.input-content input {
> 			border: 0;
> 			padding: 10px;
> 			width: 100%;
> 			height: 100%;
> 			box-sizing: border-box;
> 			/* 去除input框外边框  */
> 			outline: none;
> 			font-size: 18px;
> 		}
>  
> 		.input-content .num {
> 			position: absolute;
> 			right: 0;
> 			top: 0;
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			width: 70px;
> 			height: 100%;
> 			background: -webkit-linear-gradient(left, rgba(255, 255, 255, 0.6), rgba(255, 255, 255, 1));
> 			font-weight: bold;
> 			color: #333333;
> 		}
>  
> 		.input-content input::-webkit-input-placeholder {
> 			font-size: 18px;
> 		}
>  
> 		.input-container .send {
> 			display: flex;
> 			justify-content: center;
> 			align-items: center;
> 			width: 15%;
> 			background-color: orange;
> 			font-weight: bold;
> 		}
> 	</style>
> </head>
>  
> <body>
>  
> 	<div class="chatroom">
>  
> 		<!--左侧-->
> 		<div class="left">
> 			<!--头像-->
> 			<div class="icon-container">
> 				<img src="https://i.niupic.com/images/2018/08/10/5yxS.jpg" />
> 			</div>
>  
> 			<!--个人简介-->
> 			<div class="self-container">姓名</div>
>  
> 			<!--聊天室说明-->
> 			<div class="function-container">
> 				<div class="function-item">尬聊模式</div>
> 				<div class="function-item">“讲个笑话”</div>
> 				<div class="function-item">“歇后语”</div>
> 				<div class="function-item">“顺口溜”</div>
> 				<div class="function-item">“北京天气”</div>
> 				<div class="function-item">“名人名言”</div>
> 				<div class="function-item">“静夜思”</div>
> 			</div>
>  
> 			<div class="note-help">
> 				如果您有什么好的页面设计方案，请将您的设计稿发送至 tanabalu@qq.com ，非常感谢！
> 			</div>
> 		</div>
>  
> 		<!--右侧-->
> 		<div class="right">
> 			<!--顶部固定导航-->
> 			<div class="head">聊天室(<span id="count">0</span>)</div>
>  
> 			<!--聊天记录-->
> 			<div class="chat-container">
> 				<div class="message-other">
> 					<div class="message-container">
> 						<div class="icon">
> 							<img src="http://file06.16sucai.com/2016/0921/2b04bfeb965677fe8c2d5a4dbd292478.jpg" />
> 						</div>
> 						<div class="message-content">
> 							<div class="speaker-name">机器人</div>
> 							<div class="message">你好呀，小主人，欢迎来到TAchat。</div>
> 						</div>
> 					</div>
> 				</div>
> 				<div class="message-other">
> 					<div class="message-container">
> 						<div class="icon">
> 							<img src="http://file06.16sucai.com/2016/0921/2b04bfeb965677fe8c2d5a4dbd292478.jpg" />
> 						</div>
> 						<div class="message-content">
> 							<div class="speaker-name">机器人</div>
> 							<div class="message">
> 								<table class="message-table">
> 									<tr>
> 										<th class="message-table-th">您可尝试输入以下指令：</th>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">1、讲个笑话</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">2、歇后语</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">3、顺口溜</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">4、xx天气</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">5、名人名言</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">6、诗词</td>
> 									</tr>
> 									<tr>
> 										<td class="message-table-td">……</td>
> 									</tr>
> 								</table>
> 							</div>
> 						</div>
> 					</div>
> 				</div>
> 				<div class="message-other">
> 					<div class="message-container">
> 						<div class="icon">
> 							<img src="http://file06.16sucai.com/2016/0921/2b04bfeb965677fe8c2d5a4dbd292478.jpg" />
> 						</div>
> 						<div class="message-content">
> 							<div class="speaker-name">机器人</div>
> 							<div class="message">还可以邀请小伙伴打开本网址与您一起聊天呢！</div>
> 						</div>
> 					</div>
> 				</div>
> 			</div>
>  
> 			<!--底部输入框-->
> 			<div class="input-container">
> 				<div class="input-content">
> 					<input id="msg" autofocus="autofocus" value="" οninput="inputMessage()" placeholder="请输入聊天内容…" />
> 					<div class="num">0/30</div>
> 				</div>
> 				<div class="send" οnclick="send()">发送</div>
> 			</div>
> 		</div>
>  
> 	</div>
>  
> 	<script src="https://cdn.bootcss.com/jquery/3.2.1/jquery.min.js"></script>
> 	<script src="https://cdn.bootcss.com/socket.io/2.3.0/socket.io.dev.js"></script>
> 	<!-- <script src="jquery.particleground.min.js"></script> -->
> 	<script>
> 		// 建立连接
> 		const socket = io.connect("/");
>  
> 		// 编号
> 		let id = 0;
>  
> 		// 允许输入的最大字数
> 		const maxInput = 30;
>  
> 		// 用户头像
> 		const userIcon = 'https://i.niupic.com/images/2018/08/10/5yxS.jpg';
>  
> 		// 机器人头像
> 		const robotIcon = 'http://file06.16sucai.com/2016/0921/2b04bfeb965677fe8c2d5a4dbd292478.jpg';
>  
> 		// 用户姓名
> 		let name = '';
>  
> 		getName();
>  
> 		// 如果监听到socket消息，那么执行该回调函数，并得到广播消息
> 		// 此处的message参数是后台广播的内容
> 		socket.on("message", function (message) {
> 			console.log(message)
> 			let html = '';
> 			if (name === message.name) {
> 				html =
> 					'<div class="message-self"><div class="message-container"><div class="message-content"><div class="speaker-name">' +
> 					message.name + '</div><div class="message">' + message.msg +
> 					'</div></div><div class="icon"><img src="' + userIcon + '" /></div></div></div>';
> 			} else {
> 				html = '<div class="message-other"><div class="message-container"><div class="icon"><img src="' +
> 					userIcon + '" /></div><div class="message-content"><div class="speaker-name">' + message.name +
> 					'</div><div class="message">' + message.msg + '</div></div></div></div>';
> 			}
> 			$(".chat-container").append(html);
> 			scrollToBottom();
> 		});
>  
> 		// 接收到系统通知
> 		socket.on("joinNoticeSelf", function (message) {
> 			$("#count").text(message.count);
> 			id = message.id;
> 			$(".id").text(message.id + '号');
> 		});
>  
> 		// 接收到系统通知
> 		socket.on("joinNoticeOther", function (message) {
> 			console.log("joinNoticeOther：");
> 			console.log(message);
> 			$("#count").text(message.count);
> 			const msg = {
> 				name: message.name,
> 				action: message.action
> 			}
> 			notify(msg);
> 		});
>  
> 		// 断开连接回调事件
> 		socket.on("disconnection", function (message) {
> 			console.log(message);
> 			$("#count").text(message.count);
> 			const notifyMessage = {
> 				name: message.name,
> 				action: "退出了群聊"
> 			};
> 			notify(notifyMessage);
> 		});
>  
> 		document.onkeydown = function (event) {
> 			var e = event || window.event || arguments.callee.caller.arguments[0];
> 			if (e && e.keyCode === 13) { // enter 键
> 				send();
> 			}
> 		};
>  
> 		/**
> 		 * 发送系统通知
> 		 * 
> 		 * @param {Object} message
> 		 */
> 		function notify(message) {
> 			if (message.name && message.action) {
> 				const notify = '<div class="notify-container"><div class="notify"><span class="notify-name">' + message.name +
> 					'</span>' + message.action + '</div></div>';
> 				$(".chat-container").append(notify);
> 				scrollToBottom();
> 			}
> 		}
>  
> 		/**
> 		 * 固定滚动条到底部
> 		 */
> 		function scrollToBottom() {
> 			$(".chat-container").scrollTop($(".chat-container")[0].scrollHeight);
> 		}
>  
> 		/**
> 		 * 获取姓名
> 		 */
> 		function getName() {
> 			const str = prompt("请输入你的聊天昵称", "");
> 			if (str) {
> 				name = str;
> 				console.log(name)
> 				$(".self-container").text(str);
> 				const message = {
> 					name: name
> 				}
> 				socket.emit("join", message);
> 			} else {
> 				getName();
> 			}
> 		}
>  
> 		/**
> 		 * 输入消息
> 		 */
> 		function inputMessage() {
> 			const msg = $("#msg").val();
> 			const length = $("#msg").val().length;
> 			if (length > maxInput) {
> 				$("#msg").val(msg.substr(0, maxInput));
> 				$(".num").text(maxInput + '/' + maxInput);
> 			} else {
> 				const text = length + '/' + maxInput;
> 				$(".num").text(text);
> 			}
> 		}
>  
> 		/**
> 		 * 获取回复
> 		 */
> 		function getReply(msg) {
> 			$.ajax({
> 				url: "http://api.tianapi.com/txapi/robot/",
> 				data: {
> 					key: '762be789103e1ae7b65573f8d4fc0df6',
> 					question: msg,
> 				},
> 				success: function (res) {
> 					if (res.code === 200) {
> 						const newslist = res.newslist;
> 						for (let i = 0; i < newslist.length; i++) {
> 							const html =
> 								'<div class="message-other"><div class="message-container"><div class="icon"><img src="' +
> 								robotIcon +
> 								'" /></div><div class="message-content"><div class="speaker-name">机器人</div><div class="message">' +
> 								newslist[i].reply + '</div></div></div></div>';
> 							$(".chat-container").append(html);
> 						}
> 						scrollToBottom();
> 					}
> 				}
> 			});
> 		}
>  
> 		/**
> 		 * 发送消息
> 		 */
> 		function send() {
> 			var msg = $("#msg").val();
> 			if (!name) {
> 				getName();
> 			} else if (msg) {
> 				const message = {
> 					id,
> 					name,
> 					msg,
> 				};
> 				// 通过socket发送消息
> 				socket.send(message);
> 				getReply(msg);
> 				$("#msg").val("");
> 				$(".num").text('0/' + maxInput);
> 			}
> 		}
> 	</script>
>  
> </body>
>  
> </html>
> 
> ```
>
> 





##### 参考资料

https://zhuanlan.zhihu.com/p/58117320

https://zhuanlan.zhihu.com/p/40777409

https://zhuanlan.zhihu.com/p/29478691

https://zhuanlan.zhihu.com/p/28674204

https://zhuanlan.zhihu.com/p/54990347

https://zhuanlan.zhihu.com/p/45173862

https://zhuanlan.zhihu.com/p/20793569

https://www.jianshu.com/p/b608a765519a

https://www.zhihu.com/question/36654014

https://blog.csdn.net/weixin_41944347/article/details/88709570

https://www.cnblogs.com/demodashi/p/9442972.html

