<template>
  <div>
    <div class="title">
      <img class="logo" src="/static/images/icardlogo.png">
      <div>心愿便利贴</div>
      <button style="margin-top:200px;" open-type="getUserInfo">使用微信登陆</button>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    wx.login({
      success(res) {
        if (res.code) {
          console.log(res.code);
        }
      }
    });
  }
};
</script>

<style scoped>
.title {
  text-align: center;
}

.logo {
  width: 80px;
  height: 60px;
  display: inline-block;
  overflow: hidden;
}
</style>
