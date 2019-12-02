11月27日 星期三

用sass编写珊格系统

### 使用sass

sass 名.scss 名.css

sass --watch 名.scss:名.css

### 栅格系统

### 原理：

把屏幕宽度分成12份

### 语法

```
$width:100%;



.s{

​    width:$width;

​    height:40px;

}



.s-1{

​    float: left;

​    width:$width/12;

​    height:40px;

​    background-color:red;

}
```

