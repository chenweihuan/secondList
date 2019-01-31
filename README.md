<div align="center">

[![npm-version](https://img.shields.io/npm/v/wx-second-list.svg)](https://www.npmjs.com/package/wx-second-list)
<h1>wx-second-list</h1>
<p>一款灵活好看的微信小程序行业二级联动选择器</p>
</div>


wx-second-list使用前提：

> 使用此组件需要依赖小程序基础库 2.2.1 或以上、及开发者工具 1.02.1808300 或以上，同时依赖开发者工具的 npm 构建。具体详情可查阅[微信小程序 npm 支持文档](https://developers.weixin.qq.com/miniprogram/dev/devtools/npm.html)。

## 使用效果

![wx-second-list](./docs/wx-second-list.gif)

> PS：若想要获得上图中的效果，可参考 [test/demo](./test/demo) 中的例子实现。

## 使用方法

1. 安装 wx-second-list

```
npm install --save wx-second-list
```

2. 在需要使用 wx-second-list 的页面 page.json 中添加 wx-second-list 自定义组件配置

```json
{
  "usingComponents": {
    "secondList": "wx-second-list"
  }
}
```

3. WXML 文件中引用 wx-second-list

``` xml
<button bindtap="showSecond">弹出行业选择</button>
<secondList id="second" bind:chooseEvent = "chooseItem"></secondList>  
```

4. 在调用wx-second-list的页面page.js添加事件，可参考 [test/demo/pages/index/index.js](./test/demo/pages/index/index.js) 中的例子。
```
Page({
  data: {},
  onReady(){ this.second = this.selectComponent("#second")},
  showSecond() { this.second.showSecond()},
  chooseItem(e){ console.log('用户选择了'+e.detail) }
})
```
**secondList的属性介绍如下：**

| 属性名                   | 类型         | 默认值                    | 是否必须    | 说明                                        |
|-------------------------|--------------|---------------------------|------------|---------------------------------------------|
| id                   | String       | 无             | 是          | 组件的id                        |
| topText                  | String       | 请选择所属行业                         | 否          | 选择器最上方的文字说明                        |
| list                  | Array       | 点击[src/index.js](./src/index.js)查看                         | 否          | 选择器的内容，如果需要使用该属性，必须按照[src/index.js](./src/index.js)的格式                    |

> 如有不当或需改进之处，请君指出，感谢万分！！！
