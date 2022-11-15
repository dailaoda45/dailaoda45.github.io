---
title: HTML五种布局
---

# HTML五种布局
---
## 一、浮动布局

浮动布局的兼容性比较好，但是浮动带来的影响比较多，页面宽度不够的时候会影响布局。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>浮动布局</title>
    <style type="text/css">
      .wrap1 div{
            min-height: 200px;
        }
        .wrap1 .left{
            float: left;
            width: 300px;
            background: red;
        }
        .wrap1 .right{
            float: right;
            width: 300px;
            background: blue;
        }
        .wrap1 .center{
            background: pink;
        }  

    </style>
</head>
<body>

    <div class="wrap1">
        <div class="left"></div>
        <div class="right"></div>
        <div class="center">
            浮动布局
        </div>  
    </div>
    
</body>
</html>
————————————————
```

## 二、绝对定位布局

绝对定位布局快捷，但是有效性比较差，因为脱离了文档流。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>绝对定位布局</title>
    <style type="text/css">
      .wrap2 div{
            position: absolute;
            min-height: 200px;
        }
        .wrap2 .left{
            left: 0;
            width: 300px;
            background: red;
        }
        .wrap2 .right{
            right: 0;
            width: 300px;
            background: blue;
        }
        .wrap2 .center{
            left: 300px;
            right: 300px;
            background: pink;
        } 

    </style>
</head>
<body>

    <div class="wrap2 wrap">
        <div class="left"></div>
        <div class="center">
            绝对定位布局
        </div>
        <div class="right"></div>
    </div>

</body>
</html>
————————————————
```

## 三、flex布局

自适应好，高度能够自动撑开

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>flex布局</title>
    <style type="text/css">
      .wrap3{
            display: flex;
            min-height: 200px;
        }
        .wrap3 .left{            
            flex-basis: 300px;
            background: red;
        }
        .wrap3 .right{            
            flex-basis: 300px;
            background: blue;
        }
        .wrap3 .center{
            flex: 1;
            background: pink;
        }

    </style>
</head>
<body>

    <div class="wrap3 wrap">
        <div class="left"></div>
        <div class="center">
            flex布局
        </div>
        <div class="right"></div>
    </div>

</body>
</html>
————————————————
```

## 四、table-cell表格布局

兼容性好，但是有时候不能固定高度，因为会被内容撑高。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>table-cell表格布局</title>
    <style type="text/css">
      .wrap4{
            display: table;
            width: 100%;
            height: 200px;
        }
        .wrap4>div{
            display: table-cell;
        }
        .wrap4 .left{           
            width: 300px;
            background: red;
        }
        .wrap4 .right{          
            width: 300px;
            background: blue;
        }
        .wrap4 .center{
            background: pink;
        }

    </style>
</head>
<body>

    <div class="wrap4 wrap">
        <div class="left"></div>
        <div class="center">
            表格布局
        </div>
        <div class="right"></div>
    </div>

</body>
</html>
————————————————

```

## 五、网格布局

比较新的一种布局方式，兼容性没那么好。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>网格布局</title>
    <style type="text/css">
      .wrap5{
            display: grid;
            width: 100%;
            grid-template-rows: 200px;
            grid-template-columns: 300px auto 300px;
        }
        .wrap5 .left{   
            background: red;
        }
        .wrap5 .right{  
            background: blue;
        }
        .wrap5 .center{
            background: pink;
        }

    </style>
</head>
<body>

    <div class="wrap5 wrap">
        <div class="left"></div>
        <div class="center">
            网格布局
        </div>
        <div class="right"></div>
    </div>

</body>
</html>
————————————————
```

