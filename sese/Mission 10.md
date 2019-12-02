# Mission 10

### Html+Css 初级训练

##### css选择器

>     通配符选择器
>     元素选择器
>     ID选择器
>     类选择器
>     并集选择器(选择器分组)
>     交集选择器
>     子元素选择器
>     后代元素选择器
>     兄弟元素选择器
>     伪类选择器
>     子元素的伪类
>     伪元素选择器
>     属性选择器
>     否定伪类

##### 禅意花园攻破

> index
>
> ```html
> <!DOCTYPE html>
> <html lang="en">
> <head>
> 	<meta charset="utf-8">
> 	<title>戴夫的后花园，保卫大脑</title>
> 
> 	<link rel="stylesheet" media="screen" href="140.css">
> 	<link rel="alternate" type="application/rss+xml" title="RSS" href="http://www.csszengarden.com/zengarden.xml">
> 
> 	<meta name="viewport" content="width=device-width, initial-scale=1.0">
> 	<meta name="author" content="Dave Shea">
> 	<meta name="description" content="A demonstration of what can be accomplished visually through CSS-based design.">
> 	<meta name="robots" content="all">
> 
> 
> 	<!--[if lt IE 9]>
> 	<script src="script/html5shiv.js"></script>
> 	<![endif]-->
> </head>
> 
> <!--
> 
> 
> 
> 	View source is a feature, not a bug. Thanks for your curiosity and
> 	interest in participating!
> 
> 	Here are the submission guidelines for the new and improved csszengarden.com:
> 
> 	- CSS3? Of course! Prefix for ALL browsers where necessary.
> 	- go responsive; test your layout at multiple screen sizes.
> 	- your browser testing baseline: IE9+, recent Chrome/Firefox/Safari, and iOS/Android
> 	- Graceful degradation is acceptable, and in fact highly encouraged.
> 	- use classes for styling. Don't use ids.
> 	- web fonts are cool, just make sure you have a license to share the files. Hosted 
> 	  services that are applied via the CSS file (ie. Google Fonts) will work fine, but
> 	  most that require custom HTML won't. TypeKit is supported, see the readme on this
> 	  page for usage instructions: https://github.com/mezzoblue/csszengarden.com/
> 
> 	And a few tips on building your CSS file:
> 
> 	- use :first-child, :last-child and :nth-child to get at non-classed elements
> 	- use ::before and ::after to create pseudo-elements for extra styling
> 	- use multiple background images to apply as many as you need to any element
> 	- use the Kellum Method for image replacement, if still needed. http://goo.gl/GXxdI
> 	- don't rely on the extra divs at the bottom. Use ::before and ::after instead.
> 
> 		
> -->
> 
> <body id="css-zen-garden">
> <div class="page-wrapper">
> 
> 	<section class="intro" id="zen-intro">
> 		<header role="banner">
> 			<h1>CSS Zen Garden</h1>
> 			<h2>The Beauty of <abbr title="Cascading Style Sheets">CSS</abbr> Design</h2>
> 		</header>
> 
> 		<div class="summary" id="zen-summary" role="article">
> 			<p>A demonstration of what can be accomplished through <abbr title="Cascading Style Sheets">CSS</abbr>-based design. Select any style sheet from the list to load it into this page.</p>
> 			<p>Download the example <a href="/examples/index" title="This page's source HTML code, not to be modified.">html file</a> and <a href="/examples/style.css" title="This page's sample CSS, the file you may modify.">css file</a></p>
> 		</div>
> 
> 		<div class="preamble" id="zen-preamble" role="article">
> 			<h3>The Road to Enlightenment</h3>
> 			<p>Littering a dark and dreary road lay the past relics of browser-specific tags, incompatible <abbr title="Document Object Model">DOM</abbr>s, broken <abbr title="Cascading Style Sheets">CSS</abbr> support, and abandoned browsers.</p>
> 			<p>We must clear the mind of the past. Web enlightenment has been achieved thanks to the tireless efforts of folk like the <abbr title="World Wide Web Consortium">W3C</abbr>, <abbr title="Web Standards Project">WaSP</abbr>, and the major browser creators.</p>
> 			<p>The CSS Zen Garden invites you to relax and meditate on the important lessons of the masters. Begin to see with clarity. Learn to use the time-honored techniques in new and invigorating fashion. Become one with the web.</p>
> 		</div>
> 	</section>
> 
> 	<div class="main supporting" id="zen-supporting" role="main">
> 		<div class="explanation" id="zen-explanation" role="article">
> 			<h3>So What is This About?</h3>
> 			<p>There is a continuing need to show the power of <abbr title="Cascading Style Sheets">CSS</abbr>. The Zen Garden aims to excite, inspire, and encourage participation. To begin, view some of the existing designs in the list. Clicking on any one will load the style sheet into this very page. The <abbr title="HyperText Markup Language">HTML</abbr> remains the same, the only thing that has changed is the external <abbr title="Cascading Style Sheets">CSS</abbr> file. Yes, really.</p>
> 			<p><abbr title="Cascading Style Sheets">CSS</abbr> allows complete and total control over the style of a hypertext document. The only way this can be illustrated in a way that gets people excited is by demonstrating what it can truly be, once the reins are placed in the hands of those able to create beauty from structure. Designers and coders alike have contributed to the beauty of the web; we can always push it further.</p>
> 		</div>
> 
> 		<div class="participation" id="zen-participation" role="article">
> 			<h3>Participation</h3>
> 			<p>Strong visual design has always been our focus. You are modifying this page, so strong <abbr title="Cascading Style Sheets">CSS</abbr> skills are necessary too, but the example files are commented well enough that even <abbr title="Cascading Style Sheets">CSS</abbr> novices can use them as starting points. Please see the <a href="http://www.mezzoblue.com/zengarden/resources/" title="A listing of CSS-related resources"><abbr title="Cascading Style Sheets">CSS</abbr> Resource Guide</a> for advanced tutorials and tips on working with <abbr title="Cascading Style Sheets">CSS</abbr>.</p>
> 			<p>You may modify the style sheet in any way you wish, but not the <abbr title="HyperText Markup Language">HTML</abbr>. This may seem daunting at first if you&#8217;ve never worked this way before, but follow the listed links to learn more, and use the sample files as a guide.</p>
> 			<p>Download the sample <a href="/examples/index" title="This page's source HTML code, not to be modified.">HTML</a> and <a href="/examples/style.css" title="This page's sample CSS, the file you may modify.">CSS</a> to work on a copy locally. Once you have completed your masterpiece (and please, don&#8217;t submit half-finished work) upload your <abbr title="Cascading Style Sheets">CSS</abbr> file to a web server under your control. <a href="http://www.mezzoblue.com/zengarden/submit/" title="Use the contact form to send us your CSS file">Send us a link</a> to an archive of that file and all associated assets, and if we choose to use it we will download it and place it on our server.</p>
> 		</div>
> 
> 		<div class="benefits" id="zen-benefits" role="article">
> 			<h3>Benefits</h3>
> 			<p>Why participate? For recognition, inspiration, and a resource we can all refer to showing people how amazing <abbr title="Cascading Style Sheets">CSS</abbr> really can be. This site serves as equal parts inspiration for those working on the web today, learning tool for those who will be tomorrow, and gallery of future techniques we can all look forward to.</p>
> 		</div>
> 
> 		<div class="requirements" id="zen-requirements" role="article">
> 			<h3>Requirements</h3>
> 			<p>Where possible, we would like to see mostly <abbr title="Cascading Style Sheets, levels 1 and 2">CSS 1 &amp; 2</abbr> usage. <abbr title="Cascading Style Sheets, levels 3 and 4">CSS 3 &amp; 4</abbr> should be limited to widely-supported elements only, or strong fallbacks should be provided. The CSS Zen Garden is about functional, practical <abbr title="Cascading Style Sheets">CSS</abbr> and not the latest bleeding-edge tricks viewable by 2% of the browsing public. The only real requirement we have is that your <abbr title="Cascading Style Sheets">CSS</abbr> validates.</p>
> 			<p>Luckily, designing this way shows how well various browsers have implemented <abbr title="Cascading Style Sheets">CSS</abbr> by now. When sticking to the guidelines you should see fairly consistent results across most modern browsers. Due to the sheer number of user agents on the web these days &#8212; especially when you factor in mobile &#8212; pixel-perfect layouts may not be possible across every platform. That&#8217;s okay, but do test in as many as you can. Your design should work in at least IE9+ and the latest Chrome, Firefox, iOS and Android browsers (run by over 90% of the population).</p>
> 			<p>We ask that you submit original artwork. Please respect copyright laws. Please keep objectionable material to a minimum, and try to incorporate unique and interesting visual themes to your work. We&#8217;re well past the point of needing another garden-related design.</p>
> 			<p>This is a learning exercise as well as a demonstration. You retain full copyright on your graphics (with limited exceptions, see <a href="http://www.mezzoblue.com/zengarden/submit/guidelines/">submission guidelines</a>), but we ask you release your <abbr title="Cascading Style Sheets">CSS</abbr> under a Creative Commons license identical to the <a href="http://creativecommons.org/licenses/by-nc-sa/3.0/" title="View the Zen Garden's license information.">one on this site</a> so that others may learn from your work.</p>
> 			<p role="contentinfo">By <a href="http://www.mezzoblue.com/">Dave Shea</a>. Bandwidth graciously donated by <a href="http://www.mediatemple.net/">mediatemple</a>. Now available: <a href="http://www.amazon.com/exec/obidos/ASIN/0321303474/mezzoblue-20/">Zen Garden, the book</a>.</p>
> 		</div>
> 
> 		<footer>
> 			<a href="http://validator.w3.org/check/referer" title="Check the validity of this site&#8217;s HTML" class="zen-validate-html">HTML</a>
> 			<a href="http://jigsaw.w3.org/css-validator/check/referer" title="Check the validity of this site&#8217;s CSS" class="zen-validate-css">CSS</a>
> 			<a href="http://creativecommons.org/licenses/by-nc-sa/3.0/" title="View the Creative Commons license of this site: Attribution-NonCommercial-ShareAlike." class="zen-license">CC</a>
> 			<a href="http://mezzoblue.com/zengarden/faq/#aaa" title="Read about the accessibility of this site" class="zen-accessibility">A11y</a>
> 			<a href="https://github.com/mezzoblue/csszengarden.com" title="Fork this site on Github" class="zen-github">GH</a>
> 		</footer>
> 
> 	</div>
> 
> 
> 	<aside class="sidebar" role="complementary">
> 		<div class="wrapper">
> 
> 			<div class="design-selection" id="design-selection">
> 				<h3 class="select">Select a Design:</h3>
> 				<nav role="navigation">
> 					<ul>
> 					<li>
> 						<a href="/221/" class="design-name">Mid Century Modern</a> by						<a href="http://andrewlohman.com/" class="designer-name">Andrew Lohman</a>
> 					</li>					<li>
> 						<a href="/220/" class="design-name">Garments</a> by						<a href="http://danielmall.com/" class="designer-name">Dan Mall</a>
> 					</li>					<li>
> 						<a href="/219/" class="design-name">Steel</a> by						<a href="http://steffen-knoeller.de" class="designer-name">Steffen Knoeller</a>
> 					</li>					<li>
> 						<a href="/218/" class="design-name">Apothecary</a> by						<a href="http://trentwalton.com" class="designer-name">Trent Walton</a>
> 					</li>					<li>
> 						<a href="/217/" class="design-name">Screen Filler</a> by						<a href="http://elliotjaystocks.com/" class="designer-name">Elliot Jay Stocks</a>
> 					</li>					<li>
> 						<a href="/216/" class="design-name">Fountain Kiss</a> by						<a href="http://jeremycarlson.com" class="designer-name">Jeremy Carlson</a>
> 					</li>					<li>
> 						<a href="/215/" class="design-name">A Robot Named Jimmy</a> by						<a href="http://meltmedia.com/" class="designer-name">meltmedia</a>
> 					</li>					<li>
> 						<a href="/214/" class="design-name">Verde Moderna</a> by						<a href="http://www.mezzoblue.com/" class="designer-name">Dave Shea</a>
> 					</li>					</ul>
> 				</nav>
> 			</div>
> 
> 			<div class="design-archives" id="design-archives">
> 				<h3 class="archives">Archives:</h3>
> 				<nav role="navigation">
> 					<ul>
> 						<li class="next">
> 							<a href="/214/page1">
> 								Next Designs <span class="indicator">&rsaquo;</span>
> 							</a>
> 						</li>
> 						<li class="viewall">
> 							<a href="http://www.mezzoblue.com/zengarden/alldesigns/" title="View every submission to the Zen Garden.">
> 								View All Designs							</a>
> 						</li>
> 					</ul>
> 				</nav>
> 			</div>
> 
> 			<div class="zen-resources" id="zen-resources">
> 				<h3 class="resources">Resources:</h3>
> 				<ul>
> 					<li class="view-css">
> 						<a href="style.css" title="View the source CSS file of the currently-viewed design.">
> 							View This Design&#8217;s <abbr title="Cascading Style Sheets">CSS</abbr>						</a>
> 					</li>
> 					<li class="css-resources">
> 						<a href="http://www.mezzoblue.com/zengarden/resources/" title="Links to great sites with information on using CSS.">
> 							<abbr title="Cascading Style Sheets">CSS</abbr> Resources						</a>
> 					</li>
> 					<li class="zen-faq">
> 						<a href="http://www.mezzoblue.com/zengarden/faq/" title="A list of Frequently Asked Questions about the Zen Garden.">
> 							<abbr title="Frequently Asked Questions">FAQ</abbr>						</a>
> 					</li>
> 					<li class="zen-submit">
> 						<a href="http://www.mezzoblue.com/zengarden/submit/" title="Send in your own CSS file.">
> 							Submit a Design						</a>
> 					</li>
> 					<li class="zen-translations">
> 						<a href="http://www.mezzoblue.com/zengarden/translations/" title="View translated versions of this page.">
> 							Translations						</a>
> 					</li>
> 				</ul>
> 			</div>
> 		</div>
> 	</aside>
> 
> 
> </div>
> 
> <!--
> 
> 	These superfluous divs/spans were originally provided as catch-alls to add extra imagery.
> 	These days we have full ::before and ::after support, favour using those instead.
> 	These only remain for historical design compatibility. They might go away one day.
> 		
> -->
> <div class="extra1" role="presentation"></div><div class="extra2" role="presentation"></div><div class="extra3" role="presentation"></div>
> <div class="extra4" role="presentation"></div><div class="extra5" role="presentation"></div><div class="extra6" role="presentation"></div>
> 
> </body>
> </html>
> ```

> css
>
> ```css
> 
> 
> 
> 
> body {
> 	margin: 0;
> 	background: #444;
> 	font-family: arial, verdana, sans-serif;
> }
> .page-wrapper {
> 	position: absolute;
> 	left: 50%;
> 	top: 0;
> 	right: auto;
> 	bottom: auto;
> 	margin-left: -390px;
> 	width: 780px;
> 	clear: both;
> 	background: #F5E783 url(linklist_back.jpg) repeat-y 100% 0;
> 	border-left: solid 1px #fff;
> 	border-right: solid 1px #fff;
> }
> .page-wrapper .intro header {
> 	width: 780px;
> 	height: 311px;
> 	background: url(pageheader_p1.jpg) no-repeat 0 0;
> }
> .page-wrapper .intro header h1 {
> 	display: block;
> 	margin: 0;
> 	padding: 0;
> 	height: 311px;
> 	text-indent: -2000px;
> 	background: url(pageheader_p2.jpg) no-repeat bottom;
> }
> .page-wrapper .intro header h2 { display: none; }
> 
> .page-wrapper .intro, .page-wrapper .supporting {
> 	width: 469px;
> }
> 
> footer {
> 	position: absolute;
> 	top: 140px;
> 	right: 0;
> 	width: 260px;
> 	text-align: center;
> }
> footer a {
> 	padding: 9px 0 0 0;
> 	font-family: "Din-Medium", Arial, Helvetica, sans-serif;
> 	text-transform: uppercase;
> 	text-decoration: none;
> 	font-weight: normal;
> 	font-size: 10px;
> 	color: #fff;
> }
> footer a:hover {
> 	background: url(littlearrow.gif) no-repeat top center;
> }
> 
> .page-wrapper .sidebar {
> 	position: absolute;
> 	top: 180px;
> 	right: 0;
> 	width: 260px;
> 	background: url(linklist_bevel.jpg) no-repeat 0 0;
> }
> .page-wrapper .sidebar .wrapper {
> 	padding: 18px 35px 0 23px;
> }
> 
> .page-wrapper .sidebar h3 {
> 	margin: 10px 0 0 10px;
> 	padding: 0;
> 	width: 180px;
> 	height: 19px;
> 	text-indent: -2000px;
> }
> .page-wrapper .sidebar h3.select { background: url(t_selectadesign.jpg) no-repeat; }
> .page-wrapper .sidebar h3.archives { background: url(t_archives.jpg) no-repeat; }
> .page-wrapper .sidebar h3.resources { background: url(t_resources.jpg) no-repeat; }
> 
> .page-wrapper .sidebar ul {
> 	margin: 10px 0 20px 20px;
> 	padding: 0;
> 	list-style: none;
> }
> .page-wrapper .sidebar ul li {
> 	margin: 0 0 9px 0;
> 	padding: 0 0 0 12px;
> 	background: url(bluearrow.gif) no-repeat 0 3px;
> 	font-size: 10px;
> 	color: #fff;
> }
> 
> .page-wrapper .sidebar ul li a {
> 	text-transform: uppercase;
> 	text-decoration: none;
> 	font-size: 11px;
> 	font-weight: bold;
> 	color: #426279;
> }
> .page-wrapper .sidebar ul li a:hover { color: #21313C; }
> .page-wrapper .sidebar .design-selection ul li a { display: block; }
> .page-wrapper .sidebar .design-selection ul li a.designer-name {
> 	display: inline;
> 	text-transform: none;
> 	text-decoration: underline;
> 	color: #fff;
> 	font-weight: normal;
> 	font-size: 10px;
> }
> .page-wrapper .sidebar .design-selection ul li a.designer-name:hover { text-decoration: none; }
> 
> .page-wrapper .summary {
> 	position: relative;
> 	top: -40px;
> 	padding: 0;
> 	margin: 0 0 0 42px;
> 	font-family: "Lucida Grande", "Trebuchet MS", Verdana, Arial, sans-serif;
> }
> .page-wrapper .summary p {
> 	margin: 0 0 10px 0;
> 	font-style: italic;
> 	font-size: 17px;
> 	font-weight: bold;
> 	line-height: 18px;
> 	color: #D65200;
> }
> .page-wrapper .summary p a {
> 	text-decoration: none;
> 	color: #9E3E02;
> 	border-bottom: dotted 1px #9E3E02;
> }
> .page-wrapper .summary p a:hover {
> 	border-bottom: none;
> }
> 
> .page-wrapper .preamble h3 {
> 	margin: 0 0 0 42px;
> 	padding: 0;
> 	text-indent: -2000px;
> 	width: 299px;
> 	height: 43px;
> 	background: url(t_theroadtoenlightenment.jpg) no-repeat;
> }
> 
> .page-wrapper .preamble p, .page-wrapper .supporting p {
> 	margin: 0 0 13px 42px;
> 	font-size: 12px;
> 	line-height: 18px;
> 	color: #444;
> }
> 
> .page-wrapper .supporting p abbr {
> 	border-bottom: dotted 1px #444;
> 	cursor: help;
> }
> 
> .page-wrapper .supporting .explanation h3 {
> 	margin: 40px 0 10px 42px;
> 	padding: 0;
> 	text-indent: -2000px;
> 	width: 187px;
> 	height: 16px;
> 	background: url(t_sowhatisthisabout.jpg) no-repeat;
> }
> .page-wrapper .supporting .participation h3 {
> 	margin: 40px 0 6px 42px;
> 	padding: 0;
> 	text-indent: -2000px;
> 	width: 125px;
> 	height: 20px;
> 	background: url(t_participation.jpg) no-repeat;
> }
> .page-wrapper .supporting .benefits h3 {
> 	margin: 40px 0 10px 42px;
> 	padding: 0;
> 	text-indent: -2000px;
> 	width: 125px;
> 	height: 16px;
> 	background: url(t_benefits.jpg) no-repeat;
> }
> .page-wrapper .supporting .requirements h3 {
> 	margin: 40px 0 6px 42px;
> 	padding: 0;
> 	text-indent: -2000px;
> 	width: 125px;
> 	height: 20px;
> 	background: url(t_requirements.jpg) no-repeat;
> }
> 
> .page-wrapper .supporting .requirements p:nth-child(6) {
> 	margin: 40px 0 40px 42px;
> 	font-size: 11px;
> 	font-style: italic;
> }
> 
> .page-wrapper .preamble p a, .page-wrapper .supporting p a {
> 	text-decoration: none;
> 	color: #9E3E02;
> 	border-bottom: dotted 1px #9E3E02;
> }
> .page-wrapper .preamble p a:hover, .page-wrapper .supporting p a:hover {
> 	border-bottom: none;
> }
> ```
>
> 



##### 参考资料

[
HTML5 标签大全 ](https://www.cnblogs.com/aichiboluo/p/9327424.html)

[选择器](https://www.w3school.com.cn/cssref/css_selectors.asp)

[花园](https://www.w3school.com.cn/cssref/css_selectors.asp)

