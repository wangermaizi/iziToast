### iziToast.js使用方法
它的特点还有： 自带4种主题效果： info, warning, error 和 success。 可以自定义主题。 可以自定义图标。 可以自定义图片。 可以自定义消息通知显示的位置。 消息通知可以设置为自动关闭。 可以自定义消息通知框显示时的CSS3动画。 使用方法 在页面中引入iziToast.min.css和iziToast.min.js文件

```
<link rel="stylesheet" href="iziToast.min.css">
<script src="iziToast.min.js"></script>
```
### 初始化插件 
可以通过iziToast.show()方法来实例化一个消息通知框。

```
iziToast.show({
    title: 'Hello World!',
    message: 'I am a basic toast message!'
});
```



###  配置参数 
iziToast.js消息通知插件的默认配置参数如下：

```js
iziToast.show({
    class: '',
    title: '',
    message: '',
    color: '', // blue, red, green, yellow
    icon: '',
    iconText: '',
    iconColor: '',
    image: '',
    imageWidth: 50,
    layout: 1,
    balloon: false,
    close: true,
    rtl: false,
    position: 'bottomRight',
    target: '',
    timeout: 5000,
    pauseOnHover: true,
    resetOnHover: false,
    progressBar: true,
    progressBarColor: '',
    animateInside: true,
    buttons: {},
    transitionIn: 'fadeInUp',
    transitionOut: 'fadeOut',
    transitionInMobile: 'fadeInUp',
    transitionOutMobile: 'fadeOutDown',
    onOpen: function () {},
    onClose: function () {}
});
```

### 方法 
**settings()**方法用于设置默认值。

```js
iziToast.settings({
    timeout: 10000,
    resetOnHover: true,
    icon: 'material-icons',
    transitionIn: 'flipInX',
    transitionOut: 'flipOutX',
    onOpen: function(){
        console.log('callback abriu!');
    },
    onClose: function(){
        console.log("callback fechou!");
    }
});
```

**show()**方法用于打开一个消息通知框。
```js
 iziToast.show({
 	color: 'dark',
    icon: 'icon-person',
    title: 'Hey',
    message: 'Welcome!',
    position: 'center',
    progressBarColor: 'rgb(0, 255, 184)',
    buttons: [
        ['<button>Ok</button>', function (instance, toast) {
            alert("Hello world!");
        }],
        ['<button>Close</button>', function (instance, toast) {
            instance.hide({ transitionOut: 'fadeOutUp' }, toast);
        }]
    ]
});
```
**hide()**方法用于关闭一个消息通知框。

```js
var toast = document.querySelector('.toast');  
iziToast.hide({
    transitionOut: 'fadeOutUp'
}, toast);
```
**destroy()**方法用于销毁消息通知框。
```js
iziToast.destroy();
```
**info()**方法。

```js
iziToast.info({
    title: 'Hello',
    message: 'Welcome!',
});
```
**success()**方法。

```js
iziToast.success({
    title: 'OK',
    message: 'Successfully inserted record!',
});
```
**warning()**方法。
```js
iziToast.warning(
    { 
    	title: 'Caution', message: 'You forgot important data', 
    }
);
```
**error()**方法。

```js
iziToast.error({
    title: 'Error',
    message: 'Illegal operation',
});
```
> 事件 
**Open** - 在消息通知框打开时触发。

```js
document.addEventListener('iziToast-open', function(data){
    if(data.detail.class == 'test'){
        console.log('test open');
    }
});
```

**Close** - 在消息通知框关闭时触发。

```js
document.addEventListener('iziToast-close', function(data){
    if(data.detail.class == 'test'){
        console.log('test close');
    }
});
```


