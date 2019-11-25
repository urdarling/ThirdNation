# Mission 5

### jekyll搭建github page

##### 基本情况

*jekyll是一个简单的免费的Blog生成工具，类似WordPress。但是和WordPress又有很大的不同，原因是jekyll只是一个生成静态网页的工具，不需要数据库支持。但是可以配合第三方服务,例如Disqus。最关键的是jekyll可以免费部署在Github上*

*Github Pages 是面向用户、组织和项目开放的公共静态页面搭建托管服务，站点可以被免费托管在 Github 上，你可以选择使用 Github Pages 默认提供的域名 github.io 或者自定义域名来发布站点。Github Pages 支持 自动利用 Jekyll 生成站点，也同样支持纯 HTML 文档，将你的 Jekyll 站点托管在 Github Pages 上是一个不错的选择。*

##### 博客搭建

建立流程如下：

- 选择一个jekyll主题，fork到自己的github仓库内
- 使用gitHub的GitHub Pages，配置项目
- 设置 GitHub Pages
- 删除原有博客中内容，自己编写内容

##### 详细步骤

1. #### fork项目 进入模板的主页，点击`Fork`按钮复制代码到自己的仓库。大概1分钟左右可以完成。

2. #### 删除 CNAME 文件，CNAME 是定制域名的时候使用的内容，如果不使用定制域名会存在冲突。

3. #### 设置 GitHub Pages 点击`Settings`按钮打开设置页面，重命名项目名称为：`YourGithubUserName.github.io`

4. #### 重命名之后，再次回到`Settings` > `GitHub Pages` 页面，会发现存在这样一个地址： `https://YourGithubUserName.github.io`

5. #### 配置 _config.yml 打开项目目录下的 `_config.yml` 文件，修改以下配置：url等为你博客的地址

##### 可能遇到的模板问题

```
1.样式问题：
在md文件中 ![GIF](assets/img/fresh.gif) 表示生成一个image标签,图片找不到那应该是地址问题,通过你的描述是托管在github上,那么github的.io域名是带有一个path的,

所以你的地址前应该也加上这个path,如yourname.github.io/blog/assets/img/fresh.gif.手动加必定是繁琐的,所以可以在_config.yml中配置baseurl: blog,

```

#### jekyll原理

```
_posts 博客内容
_pages 其他需要生成的网页，如About页
_layouts 网页排版模板
_includes 被模板包含的HTML片段，可在_config.yml中修改位置
assets 辅助资源 css布局 js脚本 图片等
_data 动态数据
_sites 最终生成的静态网页
_config.yml 网站的一些配置信息
index.html 网站的入口
根据实际需要，可能还需要创建如下文件或文件夹：

_includes : 用于存放一些固定的HTML代码段，文件为.html格式，可以在模板中通过liquid标签引入，常用来在各个模板中复用如 导航条、标签栏、侧边栏 之类的在每个页面上都一样不变的内容，需要注意的是，这个代码段也可以是未被编译的，也就是说也可以使用liquid标签放在这些代码段中
image和js等自定义文件夹：用来存放一些需要的资源文件，如图片或者javascript文件，可以任意命名
CNAME文件：用来在github上做域名绑定的，将在后面介绍
favicon.ico：网站的小图标

```

```
1.我们打开根目录下的index.html可以看到：

—
layout: home-page
—
html代码段
实际上根目录下index.html运行后是home-page里面的代码内容，1中**html代码段**会填充的上图中的**content**位置
```

#### jekyll常用语法

```
{% for post in paginator.posts %} {% endfor %}表示一个for循环,百分号之间的语句为要执行的语句，该段代码表示分页输出文章，分页数量在_config.yml中配置，注意：分页只在根目录下的index.html中有效

{ site.自定义字段名称 } 表示获取_config.yml里面的自定义字段名称的值

{% for post in site.posts limit:2 %} {% endfor %}循环输出 2 篇文章

{% for post in site.posts offset:0 limit:2 %}循环输出最新2篇文章

{% for tag in post.tags %} {% endfor %}输出该篇文章里的tag

{% if link.type == site.blog_1 %} {% endfor %}字符串比较

| {% assign count = 0 %}****{% assign count = count | plus: 1 %}定义assign变量加1 |

{{post.content | strip_html | strip_newlines | truncate: 100 }}获取文章摘要，取前100个字符

2018-02-10-你要添加的描述.markdown，文章命名格式，否则识别不了

{{ page.date | date: ‘%Y, %b %d’ }}输出文章日期

{{page.title}}输出文章标题

{% if post.jekyll %} 判断文章里的jekyll字段是否为true

{% if paginator.previous_page %}是否有上一页

{% if paginator.next_page %}是否有下一页

{{ paginator.previous_page_path }}上一页url

{{ paginator.next_page_path }}下一页url

| {{ post.url | prepend: site.baseurl }}要访问的文章的url |

```



##### 参考资料

[新手搭建](https://www.jianshu.com/p/9f71e260925d)

[Jekll用法](https://segmentfault.com/a/1190000020512133)

##### 模板大全

- https://jekyll-themes.com/

- https://jekyllthemes.io/

- http://jekyllthemes.org/

- https://jamstackthemes.dev/ssg/jekyll/

- https://jekyllthemes.dev/

  