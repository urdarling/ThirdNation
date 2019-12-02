# Mission 12

### sass使用

##### sass介绍

Sass 是对 CSS 的扩展，让 CSS 语言更强大、优雅。 它允许你使用变量、嵌套规则、 mixins、导入等众多功能， 并且完全兼容 CSS 语法。 Sass 有助于保持大型样式表结构良好， 同时也让你能够快速开始小型项目， 特别是在搭配 Compass 样式库一同使用时。

```
完全兼容 CSS3
在 CSS 语言基础上添加了扩展功能，比如变量、嵌套 (nesting)、混合 (mixin)
对颜色和其它值进行操作的{Sass::Script::Functions 函数}
函数库控制指令之类的高级功能
良好的格式，可对输出格式进行定制
支持 Firebug
```

任一语法都可以导入另一种语法撰写的文件中。 只要使用 sass-convert 命令行工具，就可以将一种语法转换为另一种语法：

###### 将 Sass 转换为 SCSS
$ sass-convert style.sass style.scss

###### 将 SCSS 转换为 Sass
$ sass-convert style.scss style.sass

##### 安装

```
Sass 有三种使用方式： 命令行工具、独立的 Ruby 模块，以及包含 Ruby on Rails 和 Merb 作为支持 Rack 的框架的插件。 所有这些方式的第一步都是安装 Sass gem：

gem install sass

如果你使用的是 Windows， 就需要先安装 Ruby。

如果要在命令行中运行 Sass ,只要输入

sass input.scss output.css

你还可以命令 Sass 监视文件的改动并更新 CSS ：

sass --watch input.scss:output.css

如果你的目录里有很多 Sass 文件，你还可以命令 Sass 监视整个目录：

sass --watch app/sass:public/stylesheets

使用 sass --help 可以列出完整的帮助文档。

在 Ruby 代码中使用 Sass 是非常容易的。 安装 Sass gem 之后，你可以执行 require "sass" ， 然后就可以像这样使用 {Sass::Engine} ：

engine = Sass::Engine.new("#main {background-color: #0000ff}", :syntax => :scss)
engine.render #=> "#main { background-color: #0000ff; }\n"

```

##### sass使用

sass让人们受益的一个重要特性就是它为css引入了变量。你可以把反复使用的css属性值 定义成变量，然后通过变量名来引用它们，而无需重复书写这一属性值。或者，对于仅使用过一 次的属性值，你可以赋予其一个易懂的变量名，让人一眼就知道这个属性值的用途。

sass使用$符号来标识变量(老版本的sass使用!来标识变量。改成$是多半因为!highlight-color看起来太丑了。)，比如$highlight-color和$sidebar-width。为什么选择$ 符号呢？因为它好认、更具美感，且在CSS中并无他用，不会导致与现存或未来的css语法冲突。

sass变量的声明和css属性的声明很像：

$highlight-color: #F90;

这意味着变量$highlight-color现在的值是#F90。任何可以用作css属性值的赋值都 可以用作sass的变量值，甚至是以空格分割的多个属性值，如$basic-border: 1px solid black;，或以逗号分割的多个属性值，如$plain-font: "Myriad Pro"、Myriad、"Helvetica Neue"、Helvetica、"Liberation Sans"、Arial和sans-serif; sans-serif;。这时变 量还没有生效，除非你引用这个变量——我们很快就会了解如何引用。

与CSS属性不同，变量可以在css规则块定义之外存在。当变量定义在css规则块内，那么该变量只能在此规则块内使用。如果它们出现在任何形式的{...}块中（如@media或者@font-face块），情况也是如此：

$nav-color: #F90;
nav {
  $width: 100px;
  width: $width;
  color: $nav-color;
}

//编译后

nav {
  width: 100px;
  color: #F90;
}

在这段代码中，$nav-color这个变量定义在了规则块外边，所以在这个样式表中都可以像 nav规则块那样引用它。$width这个变量定义在了nav的{ }规则块内，所以它只能在nav规则块 内使用。这意味着是你可以在样式表的其他地方定义和使用$width变量，不会对这里造成影响。

只声明变量其实没啥用处，我们最终的目的还是使用它们。上例已介绍了如何使用 $nav-color和$width这两个变量，接下来我们将进一步探讨变量的使用方法。

- [ ] **变量引用**

凡是css属性的标准值（比如说1px或者bold）可存在的地方，变量就可以使用。css生成时，变量会被它们的值所替代。之后，如果你需要一个不同的值，只需要改变这个变量的值，则所有引用此变量的地方生成的值都会随之改变。

$highlight-color: #F90;
.selected {
  border: 1px solid $highlight-color;
}

//编译后

.selected {
  border: 1px solid #F90;
}

看上边示例中的$highlight-color变量，它被直接赋值给border属性，当这段代码被编译输出css时，$highlight-color会被#F90这一颜色值所替代。产生的效果就是给selected这个类一条1像素宽、实心且颜色值为#F90的边框。

在声明变量时，变量值也可以引用其他变量。当你通过粒度区分，为不同的值取不同名字时，这相当有用。下例在独立的颜色值粒度上定义了一个变量，且在另一个更复杂的边框值粒度上也定义了一个变量：

$highlight-color: #F90;
$highlight-border: 1px solid $highlight-color;
.selected {
  border: $highlight-border;
}

//编译后

.selected {
  border: 1px solid #F90;
}

这里，$highlight-border变量的声明中使用了$highlight-color这个变量。产生的效 果就跟你直接为border属性设置了一个1px $highlight-color solid的值是一样的。 最后，我们来了解一下变量命名的实用技巧，以结束关于变量的介绍。

##### 仿网格实例

```scss
//unit style var
$height:50px;
$pdValue:10px;
$bgColor:#78d853;
$bdColor:#461616;
$bdWidth:2px;
//reset css style
@mixin resetCSS{
	margin:0;
	padding:0;
}
//clear float
@mixin clearFix{
	content:"";
	display:table;
	clear:both;
}
//inner style
@mixin innerStyle{
	height:$height;
	background-color:$bgColor;
	border:$bdWidth solid $bdColor;
}
//outer style
@mixin outerStyle{
	box-sizing:border-box;
	float: left;
	padding:$pdValue;
}
//generate Grid
@mixin generateGrid($scr_flag){
	@if $scr_flag{
		@for $i from 1 through 12{
			.col-md-#{$i}{
				width:(100% / 12 * $i);
			}
		}
	}@else{
		@for $i from 1 through 12{
			.col-sm-#{$i}{
				width: (100% / 12 * $i);
			}
		}
	}
}
 
//style part
html,body{
	@include resetCSS;
}
.wrapper{
	box-sizing:border-box;
	width:100%;
	padding:10px;
}
.wrapper:before,.wrapper:after{
	@include clearFix;
}
.outer{
	@include outerStyle;
}
.inner{
	@include innerStyle;
}
@media (min-width:769px){
	@include generateGrid(true);
}
@media (max-width:768px){
	@include generateGrid(false);
}
```



##### 参考资料

[官网](https://www.sass.hk/guide/)

[手册](http://sass.bootcss.com/docs/sass-reference/)