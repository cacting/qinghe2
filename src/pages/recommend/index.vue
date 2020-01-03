<template>
  <div>
    <i-panel :title="title_name">
        <view style="padding: 15px;">
            <i-card v-for="item in top" :key="item" i-class="split" :title="item.name" thumb="item.jpg">
                <view slot="content">{{item.singer}}</view>
                <view slot="footer">{{item.time}}</view>
            </i-card>           
        </view>
    </i-panel>   
  </div>
</template>

<script>
import card from '@/components/card'
import top from '@/data/top.json'

export default {
  data () {
    return {
      title_name: "推荐歌单",
           
        top:[
            {name:"流行指数榜",singer:"1 透明",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:""},
            {name:"热歌榜",singer:"1 下山",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:""},
            {name:"新歌榜",singer:"1 句号",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:""},
            {name:"飙升榜",singer:"1 火红的萨日朗",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:""}
        ],
        recommand:top             
    }
  },

  components:{
    card
  },

  methods: {
      goList (url) {
          mpvue.navigateTo({ url })
      },
      goType(type){
          console.log(type)
          let url = '../list/main?type=' +type.title
          mpvue.navigateTo({ url })
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
div >>> .split{
    margin-bottom:10pt;
}
</style>


