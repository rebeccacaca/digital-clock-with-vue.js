项目源地址：[CodePen-Toshiyuki-Digital Clock with Vue.js](https://codepen.io/gau/pen/LjQwGp)

实现这个项目需要：
* 下载 Vue.js (直接在官网下载)
* 安装 Sass `npm install -g node-sass`
* 了解JS Date对象 [我的笔记参考](https://www.notion.so/Day-13-Date-f6918eaeb1d7449588b8edf825d13ba7)

这个项目涉及到的常见面试题是：如何让一个div元素水平垂直都居中？做法如下
```html
<body>
    <div>测试用的小块</div>
</body>
```
```css
div{
    background: orange;
    width: 100px;
    height: 50px;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
```

一个 `div` 就可以这样，两个及以上的话，网格布局不香吗？

下面这句也很有意思（的意思是我有点看不懂）
```css
html,body {
    height: 100%;
}
```
这样写就会在右面出现滚动条，去掉`html`背景就会变成一条一条。但是，只去掉`body`就完美了，不会出现前面两种情况。

原因：`body`元素默认有`margin：8px`(谷歌浏览器，别的不了解)。

1. `body{height:100%}`。`html`没有高度。设置`body{height:100%}`也就没啥用了，就像是你跟你爸要100块钱，但是你爸一分没有。`body`自己就剩下`8px`的`magin`了，背景颜色就是8像素、8像素重复下来的。如果设置`margin:0`，就只有纯色的背景可以显示了。

2. `html{height:100%}`。爸爸有钱儿子也跟着享福。但是默认的`margin：8px`把自己多出去一点，所以会出现滚动条。

3. `html{height:100%}`，`body{margin:0}` 这回就皆大欢喜了，儿子听话不往外跑了，爸爸也不用拿着皮带（滚动条）找他了。
