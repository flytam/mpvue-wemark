<template>
<div class="wemark_wrapper" :style='customStyle'>
<div v-for="(renderBlock,blockIndex) in wemark.renderList" :key="blockIndex">
	<div :class='renderBlock.type'>
		<div v-if="renderBlock.isArray" v-for="(renderInline,inlineIndex) in renderBlock.content" :key="inlineIndex">
			<span  :class='renderInline.type' v-if="renderInline.type === 'text' || renderInline.type === 'code' || renderInline.type === 'strong' || renderInline.type === 'deleted' || renderInline.type === 'em' || renderInline.type === 'table_th' || renderInline.type === 'table_td'">{{renderInline.content}}</span>
			<img mode="widthFix" class="_image" :src="renderInline.src" v-if="renderInline.type === 'image'"/>
		</div>
		<div v-if="!renderBlock.isArray">
			<div v-if="renderBlock.type === 'code'">{{renderBlock.content}}</div>
			<video v-if="renderBlock.type == 'video'" class="divvideo" :src="renderBlock.src" :poster="renderBlock.poster" controls></video>
		</div>
	</div>
</div>
</div>
</template>
<script>
import parse from "./parse";
export default {
  props: {
    mdData: String,
    customStyle: [String,Object]
  },
  data() {
    return { wemark: {} };
  },
  watch: {
    mdData(next) {
      this.init(next);
    }
  },
  methods: {
    init(md) {
      parse(md, this, {
        // 新版小程序可自适应宽高
        // imageWidth: wx.getSystemInfoSync().windowWidth - 40,
        name: "wemark"
      });
    }
  },
  mounted() {
    this.init(this.mdData);
  }
};
</script>

<style scoped>
.wemark_wrapper {
  margin: 10px 0;
  font-size: 32rpx;
  line-height: 1.8em;
}
.h1 {
  font-size: 40rpx;
  text-align: center;
  margin-bottom: 1em;
}
.h2 {
  font-size: 40rpx;
  padding-bottom: 0.5em;
  margin-top: 1em;
  margin-bottom: 1em;
  border-bottom: 1px solid #f0f0f0;
}
.h3 {
  font-size: 36rpx;
  margin-top: 1em;
  margin-bottom: 1em;
}
.h4,
.h5,
.h6 {
  font-weight: bold;
  margin-top: 1em;
  margin-bottom: 1em;
}
.p {
  margin-top: 1em;
  margin-bottom: 1em;
}
.video {
  margin-top: 1em;
  margin-bottom: 1em;
  width: 100%;
}
.blockquote_p {
  margin-top: 1em;
  margin-bottom: 1em;
  padding: 10px 0 10px 1em;
  font-size: 28rpx;
  background: #f0f0f0;
  border-left: 5px solid #e0e0e0;
}
.ul_li_p::before {
  content: "• ";
}
.ul_li_ul_li_p::before,
.ol_li_ul_li_p::before {
  content: "◦ ";
}
.ul_li_ul_li_p,
.ul_li_ol_li_p,
.ol_li_ul_li_p,
.ol_li_ol_li_p {
  padding-left: 1em;
}
.ul_li_p:last {
  margin-bottom: 1em;
}
.code {
  padding: 10px;
  font-size: 28rpx;
  line-height: 1.5em;
  border: 1px solid #f0f0f0;
  white-space: pre;
  overflow: auto;
}
.table_tr {
  display: flex;
  border-right: 1px solid #e0e0e0;
  border-bottom: 1px solid #e0e0e0;
}
.table_th,
.table_td {
  flex: 1;
  padding: 5px;
  font-size: 28rpx;
  border-left: 1px solid #e0e0e0;
  word-break: break-all;
}
.table_td:last {
  border-top: 1px solid #e0e0e0;
}
.table_th {
  background: #f0f0f0;
  border-top: 1px solid #e0e0e0;
}
.strong {
  font-weight: bold;
  padding: 0 5px;
  word-wrap: break-word;
}
.em {
  font-style: italic;
  padding: 0 5px;
  word-wrap: break-word;
}
.deleted {
  text-decoration: line-through;
  padding: 0 5px;
  word-wrap: break-word;
}
.image {
  width: 100%;
  height: auto;
}
.code {
  background: #f0f0f0;
  padding: 3px 5px;
  word-wrap: break-word;
}
.text {
  word-wrap: break-word;
}
</style>
