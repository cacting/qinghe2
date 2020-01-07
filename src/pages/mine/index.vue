<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>

    <i-grid>
      <i-grid-item v-for="item in grids" :key="item">
          <i-grid-icon>
              <image :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
      </i-grid-item>
    </i-grid>

    
    <i-panel i-class="split" title="新建歌单">
      <i-input :value="name" @change="changeName($event)" title="歌单名称" autofocus placeholder="请输入名称" maxlength="20" />    
    </i-panel>
    <i-button @click="handleClick" type="warning" size="default">确认新建</i-button>
    <view i-class="split" class="tips">每个人都有属于自己的特别歌单~</view>
  </div>
</template>

<script>
export default {
  data () {
    return {
      name:"",
      grids:[
        {type:'收藏',img:'/static/images/mine4.png'},
        {type:'自建歌单',img:'/static/images/mine5.png'},
        {type:'播放记录',img:'/static/images/mine6.png'}
      ]  
    }
  },

  methods: {
    changeName (event) {
      this.name = event.mp.detail.detail.value
    }, 
    handleClick () {
      if (this.name) {
        wx.showToast({
          title: '新建了' + this.name,
          icon: 'success',
          duration: 2000
        })
        // TODO:将推荐数据提交到云数据库
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
  color:rgb(105, 66, 24);
}


div >>> .no-border {
    border-width:0pt;
}

div >>> .split{
    margin-bottom:10pt;
}
</style>

</style>
