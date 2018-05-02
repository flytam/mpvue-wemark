## wemark的mpvue的适配版本

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