<template>
  <div class="about">
    <h1>{{ detailData.title }}</h1>
    <div class="main-content">
      <div class="cover">
        <img :src="getImg(detailData.cover)" alt="图片无效" />
      </div>
      <div class="content">
        {{ detailData.content }}
      </div>
    </div>
  </div>
</template>
<script>
import data from "@/static/message.json";
/* eslint-disable */
export default {
  name: "About",
  data() {
    return {
      tit: "title",
      detailData: {},
    };
  },
  created() {
    this.getData();
  },
  methods: {
    getImg(src) {
      let url = require(`@/assets/images/cover/${src}`);
      return url;
    },
    getData() {
      let tempData = data.data;
      let id = parseInt(this.$route.query.id);
      if (id) {
        let item = tempData.filter((item) => item.id === id);
        this.detailData = item[0];
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.about {
  width: 1020px;
  border-radius: 3px;
  min-height: 460px;
  margin: 0 auto;
  h1 {
    text-align: center;
  }
  .main-content{
    .cover{
      margin: 12px 0;
    }
    text-align: center;
    padding-bottom: 32px;
  }
}
</style>
