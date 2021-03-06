<template lang="md">
# PageLoading 页面加载进度条

路由页面切换、页面加载资源时提供顶部加载进度条。


> XCUI为`Vue.prototype`添加了全局方法`$PageLoading`, 如果您完整引入了XCUI， 可以直接使用如`this.$PageLoading.start()`的方式进行页面加载操作。
> 当然，您也可以使用`import PageLoading from 'xcui/lib/pageloading'` 的单组件方式调用。
> Pageloading在XCUI中被注册为一个[Vue 插件](https://vuejs.org/v2/guide/plugins.html), 在**单文件引入**时，请使用`Vue.use(PageLoading)` 挂载，再进行使用。

## DEMO


::: demo 基本使用，通过调用`.start()`、`.done()`、`.error()` 方法，实现开始，完成，错误三种操作。

```html

<tpl>
        <x-button type="primary" @click="start">start</x-button>
        <x-button type="info" @click="done">done</x-button>
        <x-button type="danger" @click="error">error</x-button>
</tpl>

```

:::

## API

```javascript
// 开始进度加载
this.$PageLoading.start();

// 结束进度加载
this.$PageLoading.done();

// 改变进度条颜色为错误色，并结束进度加载
this.$PageLoading.error();

// 设置进度条的增加速度和进度条颜色，具体描述见下
this.$PageLoading.config({
   speed: 500,
   color: '#2c96ef'
});
```

## Config Options
| 名字 | 类型 | 默认 | 描述 | 是否必选 |
|-----|-----|-----|-----|----|
|speed|Number|350|速度|可选|
|color|String|xcui主色|进度条颜色|可选|


</template>


<script>
    export default {
        methods: {
            start() {
                this.$PageLoading.start();
            },
            done() {
                this.$PageLoading.done();
            },
            error() {
                this.$PageLoading.error();
            }
        }
    };
</script>
