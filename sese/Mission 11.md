# Mission 11

### Bootstrap框架的使用

##### 框架介绍

> CSS框架，无论是哪一种，都是一种工具，它诞生的目的就是为了解决某种问题。而在页面编写的过程中最容易遇到的问题之一就是，反复解决页面样式上的兼容性问题，以及大量重复已有代码。因此有了CSS的框架将代码进行封装，提高了工作效率，让开发人员更快更好完成工作，降低工作难度，无需担心很多细枝末节的小问题。而Bootstrap就是其中的佼佼者，它算是CSS框架里名气最大的之一，虽然现在可能会有人认为太老气，但不可否认的是它依旧是流行面最广的前端框架。
>
> **支持组件：**
> 基本结构：Bootstrap 提供了一个带有网格系统、链接样式、背景的基本结构。这将在 Bootstrap 基本结构 部分详细讲解。
> CSS：Bootstrap 自带以下特性：全局的 CSS 设置、定义基本的 HTML 元素样式、可扩展的 class，以及一个先进的网格系统。这将在 Bootstrap CSS 部分详细讲解。
> 组件：Bootstrap 包含了十几个可重用的组件，用于创建图像、下拉菜单、导航、警告框、弹出框等等。这将在 布局组件 部分详细讲解。
> JavaScript 插件：Bootstrap 包含了十几个自定义的 jQuery 插件。您可以直接包含所有的插件，也可以逐个包含这些插件。这将在 Bootstrap 插件 部分详细讲解。
>
> 定制：您可以定制 Bootstrap 的组件、LESS 变量和 jQuery 插件来得到您自己的版本。
>
>     官方网站：https://getbootstrap.com/
>    
>     中文网站：http://www.bootcss.com/

##### 安装

首先要说明的是CSS框架的安装都非常简单，只需要将文件通过link的方式链接到自己的html页面当中就可以了因此官网上的安装方法都是在介绍如何获取css的代码。主要有三种方式其一是直接下载代码包，有编译后的代码，有源码，还有sass源码三种选项可供选择↓<img src="https://pic2.zhimg.com/50/v2-713830f57484c735984b9ae6eb516b1d_hd.jpg" data-caption="" data-size="normal" data-rawwidth="800" data-rawheight="323" class="origin_image zh-lightbox-thumb" width="800" data-original="https://pic2.zhimg.com/v2-713830f57484c735984b9ae6eb516b1d_r.jpg"/>其二是使用CDN加速服务，直接在页面中引用CDN文件地址即可。其三是使用各种包管理工具在本地下载安装，如bower、npm、composer等工具。

##### boot框架思想

> 学框架如果只是学习怎么使用，那将非常简单，直接把官网文档打开，复制粘贴稍稍改改就能完成任务。但如果对自己要求高一点就会发现这样做并不是一个开发者应有的学习态度。我们需要站在一个更高的地方去理解框架的设计者为什么要这么去设计，这样设计的优点缺点有哪些。如果是自己来做这样一件事应该怎么去做。通过这样的方式来学习才会有一个质的提升。Bootstrap从3起，比起之前的版本有一个非常显著的特点：因为智能手机等设备的爆发式增长，所以框架从这一个版本起，设计理念上是移动先行的。因此Bootstrap3是基于响应式设计的一套框架，又以栅格系统为及时，辅以基础的布局组件，加上多个封装完好的css组件和js插件，形成快速开发的一整套框架。从下图可以看到，这就像是一个金字塔，每一层都基于下面的基础上。<img src="https://pic4.zhimg.com/50/v2-2266f5e7749a87a758a81d2ca24335f7_hd.jpg" data-caption="" data-size="normal" data-rawwidth="646" data-rawheight="364" class="origin_image zh-lightbox-thumb" width="646" data-original="https://pic4.zhimg.com/v2-2266f5e7749a87a758a81d2ca24335f7_r.jpg"/>首先是响应式设计，它是一个非常重要的基础理念而非功能。让页面有能力响应用户的设备，让一个网站能够兼容多个终端，这样就不必为了不同设备专门去做设计和开发了。在响应式设计的基础之上，实现了我们的栅格系统，是Bootstrap框架的核心功能。栅格系统脱胎于平面排版设计，在网页设计中使用让网页更美观易读，对于开发者来讲也更加灵活规范。说到底，栅格系统其实就是把网页的总宽度均分为12份，可以自由按份来组合，以便以更简单的方式组合出不同的网页界面。在栅格的基础上，有很多基础布局的组件，比如排版、表格、按钮、表单等等，这些基础的组件可以运用于昂也的任何地方，用于构建丰富多彩兼容性极佳的网页。再在这些基础布局的基础上，添加了各式各样的css以及js组件，细化到网页的方方面面，形成了一套完整而又灵活的css框架。
>
> 

##### 网格布局

固定的位置和弹性的轨道的大小

你可以使用固定的轨道尺寸创建网格，比如使用像素单位。你也可以使用比如百分比或者专门为此目的创建的新单位 fr来创建有弹性尺寸的网格。
元素位置

你可以使用行号、行名或者标定一个网格区域来精确定位元素。网格同时还使用一种算法来控制未给出明确网格位置的元素。
创建额外的轨道来包含元素

可以使用网格布局定义一个显式网格，但是根据规范它会处理你加在网格外面的内容，当必要时它会自动增加行和列，它会尽可能多的容纳所有的列。
对齐控制

网格包含对齐特点，以便我们可以控制一旦放置到网格区域中的物体对齐，以及整个网格如何对齐。
控制重叠内容

多个元素可以放置在网格单元格中，或者区域可以部分地彼此重叠。然后可以CSS中的z-index属性来控制重叠区域显示的优先级。
Grid vs Flexbox

Grid 布局与 Flex布局有一定的相似性，都可以指定容器内部多个项目的位置。但是，它们也存在重大区别。Flex布局是轴线布局，只能指定”项目”针对轴线的位置，可以看作是一维布局。Grid布局则是将容器划分成”行”和”列”，产生单元格，然后指定”项目所在”的单元格，可以看作是二维布局。Grid布局远比Flex布局强大。不是说Grid布局取代Flex布局，实际上他俩可以很好的配合使用。

> 在Bootstrap中，栅格系统将容器均分为12份，再调整内外边距，结合媒体查询，造就了这一强大的栅格系统。其主要规则是：1、一个.row应该包含在一个.container当中，才能因为内外边距的正负抵消而有合适的对齐。2、在.row当中创建一组.column形成水平方向上的容器。3、具体内容应该放在.column中，而且只有.column可以作为.row的直接子元素。从接下来的例子上可以学到栅格相关的基础知识：
>
> ```html
> <h4>直接使用row和12column</h4><div><div class="col-md-1">1</div>...<div class="col-md-1"></div></div><h4>加上row和12column</h4><div class="row"><div class="col-md-1">2</div>...<div class="col-md-1"></div></div><h4>自由组合</h4><div class="row"><div class="col-md-3">3</div><div class="col-md-9">9</div></div><h4>列的偏移</h4><div class="row"><div class="col-md-4 col-md-offset-3">4</div></div><h4>列的嵌套</h4><div class="row"><div class="col-md-8">.col-md-8<div class="row"><div class="col-md-6">.col-md-6</div><div class="col-md-6">.col-md-6</div></div></div><div class="col-md-4"></div></div>
> ```
>
> 





##### 参考资料

[菜鸟](https://www.runoob.com/bootstrap/bootstrap-tutorial.html)

[boot简介](https://www.jqhtml.com/42602.html)

[网格系统](https://www.jqhtml.com/43528.html)

[b乎](https://www.zhihu.com/question/49296670/answer/612802976?utm_source=com.alibaba.android.rimet&utm_medium=social)

[手册](https://www.jqhtml.com/bootstraps-syntaxhigh/index.html#)

