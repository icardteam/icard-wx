<template>
  <div>
    <div class="title">
      <img class="logo" src="/static/images/icardlogo.png">
      <view style="margin-top: 100px;">
        <i-button @click="handleOpen2">无标题对话框</i-button>
      </view>
      <i-modal :visible="visible2" @ok="handleClose2" @cancel="handleClose2">
        <view>心愿便利贴将获取您的头像，昵称等公开信息</view>
      </i-modal>
      <i-button type="primary" open-type="getUserInfo">使用微信登陆</i-button>
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return {
      visible2:false
    }
  },
  methods : {
    handleOpen2(){
      this.visible2 = true;
    },
    handleClose2(){
      this.visible2 = false;
    }
  },
  mounted() {
    wx.login({
      success(res) {
        if (res.code) {
          console.log(res.code);
        }
      }
    })
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
