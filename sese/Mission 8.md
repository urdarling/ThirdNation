# Mission 8

### Nodejs基础语法

##### node小白理解

Node.js 是一个基于 Chrome V8 引擎的 Javascript 运行环境，所以说 Node.js 不是库，是一个运行环境，或者说是一个 JS 语言解释器。众所周知 javascript 是在浏览器上运行的脚本语言，主要用来控制 html 元素，即 html dom 对象，是纯粹的 客户端语言。
那么要和服务端交互，就需要等待服务端的开发人员，而服务端开发又以 java 居多，对于不了解 java　语言的前端开发人员，有的时候就不得不干等着服务端准备好，很多时候，青春就在这样的尬等中消逝了。
那么于是就有人想，如果服务端也是用 javascript 开写的话，那么前端人员不是很容易也可以开发服务端的东西了吗？ 于是就有大佬开发了一个 v8 引擎，它在服务端运行 javascript 语言，在这个基础上再进行了一定的发展，就出现了可以在服务端运行的 javascript， 它就叫做 node.js 了。
可以把 node.js 简单的看成 javascript 写的 tomcat ... 

##### nodejs的优势

既然已经有了tomcat这样的基于 java 的服务器，为什么还要有 node.js 呢？
1. node.js 上的应用可以使用 javascript 开发，这样方便前端人员
2. node.js 的 I/O 操作是非阻塞式的，比起 tomcat 这种 阻塞式 的更有优势 

##### nodejs基础语法

执行 node 命令，就可以进入 Node.js 的交互环境。

1 + 1

执行加法操作，回车，就可以看到代码正确执行了。Ctrl-D 可以退出这个交互环境。

但是更为常见的一种执行方式，是把把代码写入到一个文件中。

```js
app.js

console.log("hello");
```

然后这样来在命令行中执行

```js
node app.js
```

就可以看到 hello 被打印出来了，而这样过程跟浏览器没有一毛钱关系。

另外有一点是要特别注意的。Node.js 和浏览器是不同的环境，是有着很多细小的差异的。首先，二者各自包含的全局变量不同。document 对象是用来操作页面的，所以只有浏览器环境下才可以直接使用。但是如果是要放到 Node.js 环境下运行代码，就不要使用 document 。同样的道理，Node.js 中可以直接拿来使用的 http 对象，在浏览器环境下就没有。其次，Node.js 和浏览器对 ES6 新特性的支持程度也是不同的，这一点也要注意。

##### npm的使用

最后来聊 npm 。Node.js 引发了前后端开发的爆发，尤其是前端。 JS 开发者众多，所以贡献开源代码的人就非常多，所有这些凝结成了 npm 这个世界上最大的软件包仓库。

npm 是 Node Package Manager 的缩写，意思是 Node 的包管理系统。Nodejs 现在如日中天，其中 npm https://www.npmjs.com/ 这个功不可没。在这里，我们要实现各种功能几乎都能找到现成的别人写好的包，直接拿了用就好了。

很多 npm 包都对应一个 Github 项目，但是如果只有代码，那么使用起来还不是特别方便。而当系统上安装好了 Node.js 之后，就会配套安装一个命令，叫做 npm 。

```js
npm install moment
```

执行 npm install moment 就可以把 moment 这个包从 npm 的软件包仓库中下载这个包，然后安装到本地了。而 npm 的软件包仓库中，有数以万计的 moment 这样的包。

##### nodejs代码训练

> 正方形
>
> ```js
> function zheng(a,b,c) {
>     switch (c) {
>         case 1:
>         console.log("打印实心正方形");
>         for(var i=1;i<=a;i++){
>             for(var j=1;j<=a*2;j++){
>             process.stdout.write(b);
>             }
>             console.log()
>         }
>         break;
>         case 0:
>         console.log("打印空心正方形");
>         for(var i=1;i<=a;i++){
>             for(var j=1;j<=a*2;j++){
>                 if (i==1||i==a||j==a*2||j==1) {
>                     process.stdout.write(b);  
>                 }else{
>                     process.stdout.write(" ");  
>                 }
>                
>             }
>             console.log()
>         }
>         break;
>     }
> }    
> zheng(10,"0",1); 
> ```
>
> 梯形
>
> ```js
> function ti(a,b,c) {
>     switch (c) {
>         case 1:   
>         console.log("打印实心梯形");
>         for(var i=1;i<a;i++) {
>             for(var j=1;j<=a-i;j++) {
>                 process.stdout.write(" ");
>             }
>             for(var k=1;k<=2*i+1;k++) {
>                 process.stdout.write(b);
>             } 
>             console.log();
>         }
>         break;
>         case 0:
>         console.log("打印空心梯形");
>         for(var i=1;i<a;i++) {
>             for(var j=1;j<=a-i;j++) {
>                 process.stdout.write(" ");
>             }
>             for(var k=1;k<=2*i+1;k++) {
>                 if (i==1||i==a-1||k==1||k==2*i+1) {
>                     process.stdout.write(b);  
>                 }
>                 else{
>                         process.stdout.write(" ");
>                     }
>                 }    
>             console.log();
>         }
>     }
> }
> ti(10,"*",1);
> ```
>
> 三角形
>
> ```js
> function san(a,b,c) {
>    switch (c) {
>       case 1:
>       console.log("打印实心三角形");
>       for(var i=1;i<=a;i++){
>          for(var j=1;j<=a-i;j++){
>             process.stdout.write(" ");
>          }
>          for(var k=1;k<=2*i-1;k++){
>             process.stdout.write(b);
>          }
>          console.log()
>       }
>       break;
>       case 0:
>       console.log("打印空心三角形");
>       for(var i=0;i<=a;i++){
>          for(var j=1;j<=a-i;j++){
>             process.stdout.write(" ");
>          }
>          for(var k=1;k<=2*i-1;k++){
>             if (i==1||i==a||k==1||k==2*i-1) {
>                process.stdout.write(b);
>             }else{
>                   process.stdout.write(" ");          
>             }  
>          }
>          console.log()
>       }
>       break; 
>    }
> }
> san(7,"*",1);
> ```
>
> 菱形
>
> ```js
> function ling(a,b,c) {
>    switch (c) {
>        case 1:
>       console.log("打印实心菱形");
>       for(var i=1;i<=a;i++){
>          for(var j = 1; j <= a - i; j++){
>             process.stdout.write(" ");
>          }
>          for(var k=1;k<=2*i-1;k++){
>             process.stdout.write(b);
>          }
>          console.log()
>       }
>       for(var i=a-1;i>=1;i--){
>          for(var j=1;j<=a-i;j++){
>             process.stdout.write(" ");
>          }
>          for(var k=1;k<=2*i-1;k++){
>             process.stdout.write(b);
>          }
>          console.log()
>       }
>       break;
>       case 0:
>       console.log("打印空心菱形");
>       for (var i = 1; i <= a; i++) {
>          // 打印上半部分空格
>          for (var j = 1; j <= a - i; j++) {
>             process.stdout.write(" ");
>          }
>          // 打印原本实心的*部分
>          for (var k = 1; k <= 2 * i - 1; k++) {
>             // 仅在一行的开头和末尾打印*
>             if (k == 1 || k == 2 * i - 1) {
>                process.stdout.write(b);
>             } else {
>                process.stdout.write(" ");
>             }
>          }
>          console.log();
>       }
>       for (var i = a-1; i >= 1; i--) {
>          // 打印下半部分空格
>          for (var j = 1; j <= a - i; j++) {
>             process.stdout.write(" ");
>          }
>          // 打印原本实心的*部分
>          for (var k = 1; k <= 2 * i - 1; k++) {
>             // 仅在一行的开头和末尾打印*
>             if (k == 1 || k == 2 * i - 1) {
>                process.stdout.write(b);
>             } else {
>                process.stdout.write(" ");
>             }
>          }
>          console.log();
>       }
>       break;
>    }
> }
> ling(7,"*",1);
> ```
>
> 回
>
> ```js
> function hui(a,b,c) {
>     switch (c) {
>         case 1:
>         console.log("打印实心回形");
>         for(var i=1;i<=a;i++){
>             for(var j=1;j<=a*2;j++){
>                 if (i==1||i==a||j==a*2||j==1||(i>2&&i<a-1&&j>3&&j<a*2-2)) {
>                     process.stdout.write(b);  
>                 }else{
>                     process.stdout.write(" ");  
>                 }            
>             }
>             console.log()
>         }
>         break;
>         case 0:
>         console.log("打印空心回形");
>         for(var i=1; i<=a; i++){
>             for(var j=1; j<=a*2; j++){
>                 if(i==1||i==a||((i==3||i==a-2)&&(j>3&&j<a*2-2))){
>                 process.stdout.write("*");
>                 }
>                 else{
>                     if(j==1||j==a*2||((j==4||j==a*2-3) && (i>2&i<=a-2))){
>                     process.stdout.write("*");
>                     }else{
>                     process.stdout.write(" ");
>                     }
>                 }
>             }
>             console.log();
>         }
>         break;
>     }
> }
> hui(10,"*",1);
> ```
>
> 合并数组为字符串
>
> ```js
> function xsplit(str,s){
>     var len = 0;
>     var sub = '';
>     while(len<str.length){
>         if (len==str.length-1) {
>             sub += str[len];
>             
>         } else {
>             sub += str[len];
>             sub +=s;
>         }            	                             
>         len++;
>     }
>     console.log(sub);
>     
> }
> xsplit(['a','b','c','d','e','r','d'],'77');
> 
> 
> ```
>
> 以标号分割字符串
>
> ```js
> function jie(str,a,b){
>     var sub='';
>     for(var i = a;i<str.length;i++){//从a下标开始截取，到b下标停止，将a到b的字符放入sub
>         sub = sub+str[i];
>         if(i==b){
>             break;
>         }
>     }
>     console.log(sub);
> }
> jie('hgiwhroighgiurhglrkghkjrwg','2','4');
> 
> ```
>
> 以字符分割字符串为数组
>
> ```js
> function divide(str, sub) {
>     var arr = new Array;
>     var newstr = '';
>     var x = 0;
>     for(var i = 0; i < str.length; i ++){//遍历传入的字符串
>         var strs = '';
>         var k = i;
>         for(var j = 0; j < sub.length; j ++) {//遍历要分割的字符串
>             if(str[k] == sub[j]){//当遍历到有字符串与分隔符相等时，将下标对应字符传入一个临时字符串，增加下标后继续对比。
>                 strs += str[k];
>                 k++;
>                 if(strs == sub){//当临时字符串和分隔符完全相等时，newstr传入arr数组
>                     arr[x] = newstr;
>                     i = i + sub.length-1 ;//i下标增加sub的长度后继续遍历
>                     newstr = '';//重置newstr
>                     x++;
>                 }
>             }else{//如果不相等将字符串传入newstr 跳出后进入i循环继续对比
>                 newstr += str[i];
>                 break;
>             } 
>         }
>         if(i == str.length - 1){//遍历完毕后将最后一次newstr给arr数组
>             arr[x] = newstr;
>         }   
>     }
>     console.log(arr);
> }
> divide('ab,cccddd,fds,few,tyt45y,54y,5y45', ',');
> ```
>
> 字符串查找
>
> ```js
> function search(str1, str2) {
>     var b;
>     for (var i = 0; i < str1.length; i++) {//遍历str1
>         b = '';
>         var k = i;
>         for (var j = 0; j < str2.length; j++) {//遍历str2，如果str1和str2某个字符相同则继续对比，如果完全相同则打印第一个i下标，
>             if (str1[k] == str2[j]) {
>                 b += str1[k++];
>                 if (b == str2) {
>                     console.log(i);
>                 }
>             } 
>         }        
>     }
> }
> search('12345612347iuh34hiuhiuhiu34', '34');
> ```
>
> 字符串长度
>
> ```js
> function lenth(s) {
>     var str=s;
>     var i=0;
>     while (str[i]!=undefined) {
>         i++;        
>     }
>     console.log(i+"");  
> }
> lenth("ewgregr");
> ```
>
> 





##### 参考资料：

[菜鸟node](https://www.runoob.com/nodejs/nodejs-tutorial.html)