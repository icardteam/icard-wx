<template>
  <div>
    <div class="title">
      <img class="logo" src="/static/images/icardlogo.png">
      <i-button style="margin-top:200px;" open-type="getUserInfo">使用微信登陆</i-button>
      <!--<i-modal title="微信授权" :visible="visible2" @ok="handleOk" @cancel="handleCancel">
        <view class="headtext">心愿便利贴申请获得以下权限：</view>
        <view>
          <input type="checkbox" disabled checked>
          <span style="font-size: 0.7rem">获得您的公开信息(昵称、头像等)</span>
        </view>
      </i-modal>-->
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return {
      visible2:true
    }
  },
  methods : {
    handleOk(){
      this.visible2 = false;
    },
    handleCancel(){
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
  margin-top: 1rem;
  width: 1.2rem;
  height: 1.2rem;
  display: inline-block;
}

.headtext {
  font-weight: 700;
}

view {
  margin: 0 0.5rem;
}
</style>
