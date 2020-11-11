<template>
  <div class="home cover-wrap">
    <!--获取数据-->
    <el-row :gutter="20">
      <el-col :span="8" v-for="(item, index) in data" :key="index">
        <div class="grid-content bg-purple">
          <router-link :to="{ name: 'About', query: { id: item.id } }">
            <img :src="getImg(item.cover)" alt="图片无效" />
            <p class="title">{{ item.title }}</p>
          </router-link>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import data from "@/static/message.json";
/* eslint-disable */
export default {
  name: "Home",
  data() {
    return {
      data: {},
    };
  },
  created() {
    this.getData();
  },
  methods: {
    getImg(src) {
      let url = require(`@/assets/images/cover/${src}`)
      return url;
    },
    getData() {
      let tempData = JSON.parse(JSON.stringify(data.data));
      this.data = tempData;
    },
  },
};
</script>
<style lang="scss" scoped>
.home {
  max-width: 1180px;
  margin: 0 auto;
  padding: 30px 0 48px 0;
  &.cover-wrap {
    .grid-content {
      padding: 18px;
      background-color: #fff;
      border-radius: 3px;
      margin-top: 20px;
      .title {
        text-align: left;
        line-height: 28px;
        height: 56px;
        color: #000;
        display: block;
        margin: 0;
        padding-top: 12px;
      }
      img {
        max-width: 100%;
        max-height: 100%;
      }
    }
  }
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
}
</style>
