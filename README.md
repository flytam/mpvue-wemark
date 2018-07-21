## wemark 的 mpvue 的适配版本

[![NPM version][npm-image]][npm-url]
[![David deps][david-image]][david-url]
[![npm download][download-image]][download-url]
[![npm license][license-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/mpvue-wemark.svg?style=flat-square
[npm-url]: https://npmjs.org/package/mpvue-wemark
[travis-image]: https://img.shields.io/travis/673800357/mpvue-wemark.svg?style=flat-square
[travis-url]: https://travis-ci.org/673800357/mpvue-wemark
[coveralls-image]: https://img.shields.io/coveralls/673800357/mpvue-wemark.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/673800357/mpvue-wemark?branch=master
[david-image]: https://img.shields.io/david/673800357/mpvue-wemark.svg?style=flat-square
[david-url]: https://david-dm.org/673800357/mpvue-wemark
[node-image]: https://img.shields.io/badge/node.js-%3E=_4.0-green.svg?style=flat-square
[node-url]: http://nodejs.org/download/
[download-image]: https://img.shields.io/npm/dm/mpvue-wemark.svg?style=flat-square
[download-url]: https://npmjs.org/package/mpvue-wemark
[license-image]: https://img.shields.io/npm/l/mpvue-wemark.svg

在 mpvue 中进行 markdown 的解析

[原库 wemark](https://github.com/TooBug/wemark)

**本库不再维护**。wemark 2.0 作者重构后已支持在 mpvue 中进行使用.详情请看原库。当然如果你想通过 npm 便捷使用也可以使用本库的。

#### 使用方法

```
npm i mpvue-wemark
```

```vue
<template>
  <div>
    <wemark :mdData='mdData' customStyle='background-color:white;'/>
  </div>
</template>

<script>
import wemark from "mpvue-wemark";
export default {
  data() {
    return {
      mdData: ""
    };
  },
  components: {
    wemark
  },
  mounted() {
    this.mdData = "## hello, world";
  }
};
</script>
```

#### 更新记录

v1.1.2 添加自定义样式 传入 customStyle 属性，按照 mpvue 的支持写法。修复# 输入的报错

#### 感谢

[感谢原作者 toobug 的支持](https://github.com/TooBug)

#### LICENSE

MIT
