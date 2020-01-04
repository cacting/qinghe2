<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px">
      <block v-for="item in imgUrls" :key="item">            
        <swiper-item>
          <image :src="item" style="width:100%;"/>
        </swiper-item>
      </block>
    </swiper>
    <i-grid>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/ashuxiang.jpg" />
      </i-grid-icon>
      <i-grid-label>书香古韵</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/alaba.jpg" />
      </i-grid-icon>
      <i-grid-label>腊八年味</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/apinbo.jpg" />
      </i-grid-icon>
      <i-grid-label>拼搏生活</i-grid-label>
    </i-grid-item>
    </i-grid>

    <i-panel title="猜你喜欢">
        <view style="padding: 10px;">
           <i-cell-group>             
              <i-cell title="下山" is-link url="/pages/index"></i-cell>                            
            </i-cell-group>
            <i-cell-group>
              <i-cell title="句号" is-link url="/pages/index"></i-cell>             
            </i-cell-group>
            <i-cell-group>
              <i-cell title="透明" is-link url="/pages/index"></i-cell>
            </i-cell-group>
            <i-cell-group>
              <i-cell title="关闭推荐">
                  <switch slot="footer" checked />
              </i-cell>
            </i-cell-group>
        </view>                                      
    </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {        
        imgUrls: [
        'http://www.canyin88.com/uploads/image/2019/04/16/1555378220872933.jpg',
        'http://www.canyin88.com/uploads/image/2019/04/15/1555321255843942.jpg',
        'http://www.canyin88.com/uploads/190415/99ad8154e7332ca96ccb323580b3b8a2_3.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000  
    }
  },

  methods: {
      goType(type){
          console.log(type)
          let url = '../list/main?type=' +type.title
          mpvue.navigateTo({ url })
      }
  },

  created () {
      //let app =getApp()
  }
}
</script>

<style scoped>
div >>> .no-border {
    border-width:0pt;
}
div >>> .split{
    margin-bottom:10pt;
}
</style>
