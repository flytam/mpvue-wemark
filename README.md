## wemark的mpvue的适配版本

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

在mpvue中进行markdown的解析

[wemark](https://github.com/TooBug/wemark)作者链接

#### 使用方法
```
npm i mpvue-wemark
```


```vue
<template>
  <div>
    <wemark :mdData='mdData'/>
  </div>
</template>

<script>
import wemark  from "mpvue-wemark";
export default {
  data() {
    return {
      mdData: ''
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
#### 感谢

[感谢原作者支持](https://github.com/TooBug)

#### LICENSE
MIT