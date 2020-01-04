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

    <i-grid i-class="no-border">
      <i-grid-item @click="goList(item.url)" i-class="no-border" v-for="item in grids" :key="item">
          <i-grid-icon>
              <image :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
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
        '/static/images/lun1.jpg',
        '/static/images/lun2.jpg',
        '/static/images/lun3.jpg',
        '/static/images/lun4.jpg',
        '/static/images/lun5.jpg',
        '/static/images/lun6.jpg',
        '/static/images/lun7.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
      grids:[
        {type:'书香古韵',img:'/static/images/ashuxiang.jpg',"url":'../list/main?type=1'},
        {type:'腊八年味',img:'/static/images/alaba.jpg',"url":'../list/main?type=2'},
        {type:'拼搏生活',img:'/static/images/apinbo.jpg',"url":'../list/main?type=3'}
      ]  
    }
  },

  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType(type){
        console.log(type)
        let url = '../list/main?type=' +type
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
