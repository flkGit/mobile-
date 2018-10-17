# 移动端开发小技巧


### HTML模板
***
<code>
	meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no"

	<script>
	document.documentElement.style.fontSize = document.documentElement.clientWidth / 7.5 + 'px';
	</script>
</code>

***

> 我们知道：
> 设备像素 = 设计图尺寸 = 750px
> 布局视口 = 375px
> 假设我们以iPhone6设计图尺寸为标准，在设计图的尺寸下设置一个font-size值为100px。
***
> 也就是说：750px宽的页面，我们设置100px的font-size值，那么页面的宽度换算为rem就等于 750 / 100 = 7.5rem。
> 我们就以页面总宽为7.5rem为标准，那么在布局视口中，也就是页面总宽为375px下，font-size值应该是多少？很简单：
***
> 这样，无论在什么设备下，我们页面的总宽度都是7.5rem，所以我们直接在设计图上测量px单位的尺寸，然后除以100转换成rem单位后直接使用就可以了，比如，在iPhone6设计图中测量一个元素的尺寸为200px，那么转换成rem单位就是 200 / 100 = 2rem，因为在不同设备下我们动态设置了html标签的font-size值，所以不同设备下相同的rem值对应的像素值是不同的，这样就实现了在不同设备下等比缩放。我们修改html代码如下：

***
### 文字字体大小是不要换算成rem做单位的，而是使用媒体查询来进行动态设置
#### CSS代码段
<code>
@media screen and (max-width: 321px) {
    body {
        font-size:16px
    }
}

@media screen and (min-width: 321px) and (max-width:400px) {
    body {
        font-size:17px
    }
}

@media screen and (min-width: 400px) {
    body {
        font-size:19px
    }
}
</code>