## wemark的mpvue的适配版本

[wemark](https://github.com/TooBug/wemark)作者链接

#### 使用方法
```
npm i mpvue-wemark
```

详细使用参数可以参考[wemark](https://github.com/TooBug/wemark)
```vue
<template>
  <div>
    <wemark :mdData='mdData'/>
  </div>
</template>

<script>
import wemark  from "@/components/wemark";
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