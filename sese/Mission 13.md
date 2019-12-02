# Mission 13

### h5+css完成威信界面

##### 弹性盒子

弹性盒子是 CSS3 的一种新的布局模式。

CSS3 弹性盒（ Flexible Box 或 flexbox），是一种当页面需要适应不同的屏幕大小以及设备类型时确保元素拥有恰当的行为的布局方式。

引入弹性盒布局模型的目的是提供一种更加有效的方式来对一个容器中的子元素进行排列、对齐和分配空白空间。 

> flex-grow、flex-shrink、flex-basis三个属性的作用：
>
> 在flex布局中，父元素在不同宽度下，子元素是如何分配父元素空间的。
>
> (注意：这三个属性都是在子元素上设置的，下面小编要讲的是父元素，指以flex布局的元素(display:flex))
>
> 小编这里先教一下大家如何快速记住这三个属性：
>
> 首先是   flex-basis  ，basis英文意思是<主要成分>，所以他和width放在一起时,肯定把width干掉，basis遇到width时就会说我才是最主要的成分，你是次要成分，所以见到我的时候你要靠边站。
>
> 其次是   flex-grow，grow英文意思是<扩大，扩展，增加>,这就代表当父元素的宽度大于子元素宽度之和时，并且父元素有剩余，这时，flex-grow就会说我要成长，我要长大，怎么样才能成长呢，当然是分享父元素的空间了。见下面第二个属性的内容
>
> 最后是   flex-shrink， shrink英文意思是<收缩，>，这就代表当父元素的宽度小于子元素宽度之和时，并且超出了父元素的宽度，这时，flex-shrink就会说外面的世界太苦了，我还是回到父亲的怀抱中去吧！因此，flex-shrink就会按照一定的比例进行收缩。见下面第三个属性的内容
> 

##### 相对定位和绝对定位

> 一、position 的四个值：static、relative、absolute、fixed。
>
> 绝对定位：absolute 和 fixed 统称为绝对定位
>
> 相对定位：relative
>
> 默认值：static
> 二、relative定位与absolute定位的区别
>
> 实例：
>
> HTML代码：
>
> css代码：
>
> 初始效果：
>
> 1、relative：相对于原来位置移动，元素设置此属性之后仍然处在文档流中，不影响其他元素的布局
>
> 给第二个box设置relative：
>
> 元素相对于原来位置偏移，宽高都没变，撑大了容器。
>
> 2、absolute:元素会脱离文档流，如果设置偏移量，会影响其他元素的位置定位
>
> 只给第五个box设置absolute：
>
> 说明：元素在没有定义宽度的情况下，宽度由元素里面的内容决定，效果和用float方法一样。
>
>  absolute定位原理剖析：
>
> 1.在父元素没有设置相对定位或绝对定位的情况下，元素相对于根元素定位（即html元素）（是父元素没有）。
>
> 现在给box5偏移值来验证：
>
> 2.父元素设置了相对定位或绝对定位，元素会相对于离自己最近的设置了相对或绝对定位的父元素进行定位（或者说离自己最近的不是static的父元素进行定位，因为元素默认是static）。
>
> 补充：网上有人解释为元素会相对于第一个不是static的父元素定位，我觉得这很容易让人产生误解。以上是我自己的定义。
>
> 现在给body元素一个绝对定位（body元素设置为了absolute，整个容器的宽度由最长div决定，宽度变小了）：
>
> 此时的box5现在相对于body元素定位
>
> 我把上面相对于html元素定位和相对于body定位的两张图放在一起，对比可以看到下面的图，相对于body定位的box5距离文字box1要远一点。所以在没有父元素设置相对定位或绝对定位的情况下，设置了absolute的元素会相对于html根元素定位。
>
> css代码：
>
> 再来验证这句话：父元素设置了相对定位或绝对定位，元素会相对于离自己最近的设置了相对或绝对定位的父元素进行定位
>
> 现在给box们套三个父容器，如下：
>
> html代码：
>
> 三个父容器的css样式如下：
>
>  现在的样子，现在的box5并不是所说的相对于第一个不是static的元素定位（按这句话的说法，现在我的box5应该相对于最外层容器1偏移才对），而是相对于离自己最近的一层的设置了相对或绝对定位的父元素定位：
>
> 现在把第二个容器和第三个容器的position注释掉（没有position，设置top、left、bottom、right值都没有效），结果如下：
>
> 现在box5的外层设置了相对或绝对的父元素只有最外层容器1，所以box5现在相对于最外层容器1定位。（明显box5移动了）
>
> 现在只注释掉第三个容器的position
>
> 原理也是一样，现在相对于第二个容器定位（top：50px，离自己最近的设置了相对或绝对定位的父元素）：
>
>  上面第二个和第三个容器都设置的是相对定位，现在改成绝对定位：
>
> css代码：
>
> 原理和把第二、第三个容器设置为relative一样，只是设置为absolute了之后，第三个容器包含着内容一起脱离了文档，所以没有撑开外面两层容器的宽度
>
> 现在的效果：
>
>  外面再添一个容器，来验证上面第一、第二没有被撑开的效果
>
> 宽度受到上一层的父容器的宽度限制，现在拉宽第一层的容器的宽度，第二层和第三层随之变宽，效果如下：
>
>  
>
> 但是如果容器里面有长的div，容器仍然可以被撑开，效果如下：
>
>  补充：
>
> box2设置为absolute定位之后，脱离文档流，box3向上移，左边被box2遮盖了。
>
>  
>
>  在上面的基础上，box3设置absolute，box3脱离文档流（就好像box3浮起来了一样，浮在了box2上面），box4往上移，box3盖住box2，和部分box4.
>
>  同理如果box4设置了绝对定位，就会浮起来盖住box3和box2。
> 总结
>
> relative：定位是相对于自身位置定位（设置偏移量的时候，会相对于自身所在的位置偏移）。设置了relative的元素仍然处在文档流中，元素的宽高不变，设置偏移量也不会影响其他元素的位置。最外层容器设置为relative定位，在没有设置宽度的情况下，宽度是整个浏览器的宽度。
>
> absolute：定位是相对于离元素最近的设置了绝对或相对定位的父元素决定的，如果没有父元素设置绝对或相对定位，则元素相对于根元素即html元素定位。设置了absolute的元素脱了了文档流，元素在没有设置宽度的情况下，宽度由元素里面的内容决定。脱离后原来的位置相当于是空的，下面的元素会来占据位置。 



##### 参考资料

[定位](https://www.cnblogs.com/yy95/p/5672440.html)

[flexbox](https://www.cnblogs.com/ZheOneAndOnly/p/10847591.html)

[常用参数](https://www.cnblogs.com/lijiapeng/p/9923934.html)

[弹性盒子](https://blog.csdn.net/m0_37058714/article/details/80765562)

[布局](https://www.cnblogs.com/NiuBiHH/p/9575604.html#_lab2_0_0)