<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>
    <i-panel title="来创建属于自己的歌单吧">
      <i-input :value="name" @change="changeName($event)" title="歌单名称" autofocus placeholder="请输入名称" maxlength="20" />
      <i-input :value="state" @change="changeState($event)" title="简介" autofocus placeholder="请输入简介" maxlength="20" />
    </i-panel>
    <i-button @click="handleClick" type="warning" size="default">添加歌单</i-button> 
    <view class="tips">每个人都应该有一个属于自己的歌单</view>  
  </div>
</template>

<script>
export default {
  data () {
    return {
      name:"",
      state:""
    }
  },

  methods: {
    changeName (event) {
      this.name = event.mp.detail.detail.value
    },
    changeState (event) {
      this.state = event.mp.detail.detail.value
    },
    handleClick () {
      if (this.name && this.state) {
        wx.showToast({
          title: '已新建' + this.name,
          icon: 'success',
          duration: 2000
        })
        // TODO:将推荐数据提交到云数据库
      } else {
        wx.showToast({
          title: '信息不完整',
          icon: 'none',
          duration: 2000
        })
      }
    }
  },

  created () {
  }
}
</script>

<style scoped>
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #666;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}

.tips {
  padding: 20pt;
  font-size: 10pt;
  color:darkorange;
}


</style>
