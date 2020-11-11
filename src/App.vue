<template>
  <div id="app" class="app-container">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <router-view />
    <div class="footer">
      <p>
        @2020
        <span
          style="cursor: pointer;"
          @click="link('https://beian.miit.gov.cn')"
          >粤ICP备20038889号</span
        >
      </p>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    link(url) {
      window.open(url, "_blank");
    },
  },
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
body {
  background-color: #f6f7f9;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.app-container {
  .footer {
    text-align: right;
    font-size: 12px;
    position: fixed;
    bottom: 0;
    right: 0;
    line-height: 38px;
    padding-right: 20px;
    color: #7e7e7e;
  }
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: orange;
}

</style>
