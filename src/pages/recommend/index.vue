<template>
  <div>
    <i-panel i-class="split1" title="排行榜">
        <view style="padding: 15px;">
          
            <i-card @click="goList(item.url)" i-class="split2" v-for="item in top" :key="item" :title="item.type" :thumb="item.img">
                <view slot="footer">1.{{item.song1}}</view>
                <view slot="footer">2.{{item.song2}}</view>
                <view slot="footer">3.{{item.song3}}</view>
            </i-card>           
        </view>
    </i-panel>   
  </div>
</template>


<script>
export default {
  data () {
    return {                 
        top:[
            {type:"流行指数榜",img:"/static/images/bliuxing.jpg",song1:"透明",song2:"凌晨两点的北京",song3:"炸山姑娘",url:'../list/main?type=4'},
            {type:"热歌榜",img:"/static/images/brege.jpg",song1:"下山",song2:"句号",song3:"透明",url:'../list/main?type=5'},
            {type:"新歌榜",img:"/static/images/bxinge.jpg",song1:"句号",song2:"火红的萨日朗",song3:"透明",url:'../list/main?type=6'},
            {type:"飙升榜",img:"/static/images/bbiaos.jpg",song1:"嚣张",song2:"忘情牛肉面",song3:"逃爱",url:'../list/main?type=7'}
        ]            
    }
  },


  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType(type){
        console.log(type)        
    }
  },

  created () {      
  }
}
</script>

<style scoped>
div >>> .no-border {
    border-width:0pt;
}
div >>> .split1{
    margin-bottom:8pt;
}
div >>> .split2{
    margin-bottom:10pt;
}
</style>


