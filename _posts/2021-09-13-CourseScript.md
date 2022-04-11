---
date : 2021-09-13
layout : post
tags : 科大
title : 选课脚本说明 
---

### 一、首先进入选课页面

![image-20210913125143806](https://s2.loli.net/2022/04/10/vRriJBc3bIlFkeu.png)

### 二、然后想选哪一门课，先搜索出来

比如我这里想选择高级计算机图形学

![image-20210913125232340](https://s2.loli.net/2022/04/10/pr9648hCSdRQmFi.png)

### 三、在当前页面打开检查（Chrome浏览器中按F12）

![image-20210913125336933](https://s2.loli.net/2022/04/10/oYMve2K8gOcGBfh.png)

### 四、设置脚本

1、首先在检查中，点击Console

2、粘贴以下js代码：

```javascript
setInterval(function() {
    var buttons = document.querySelectorAll("button[class='btn btn-primary course-select']");
    var button = buttons[0]
    button.click();
    setInterval(function() {
        var button1 = document.querySelector("button[class='btn btn-default close-modal']");
        button1.click();
},5000);
},10000);
```

3、js代码说明：

代码会一直循环运行，模拟人点击选课按钮以及关闭按钮，每隔10s一次；

注意上述代码中

```javascript
var button = buttons[0]
```

这一行可以进行修改，0代表的就是从上到下第一个按钮

如果该门课有多个可以选择的，可以新开一个页面，修改这个数字，同时跑多个

### 五、脚本运行示例

![image-20210913130003743](https://s2.loli.net/2022/04/10/jZpBDnsTHgLXe3r.png)

### 六、注意事项

1.确保自己先在全部课程中搜索出你想选的那门课，在那门课出来的页面中，进行脚本运行操作

2.脚本运行后若想关闭，直接关闭网页即可