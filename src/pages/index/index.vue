<template>
  <div>
    <i-grid i-class="no-border">
        <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
            <i-grid-icon>
             <image :src="grid.image" />
         </i-grid-icon>
         <i-grid-label>{{grid.title}}</i-grid-label>
        </i-grid-item>
        <i-grid-item i-class="no-border">
            <i-grid-icon>
                <image src="/static/images/6.png" />
            </i-grid-icon>            
        </i-grid-item>
    </i-grid>

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
export default {
  data () {
    return {
        title_name: "推荐歌单",
        grids:[
            {title:"红歌",image:"/static/images/5.png"},
            {title:"流行",image:"/static/images/6.png"},
            {title:"古典",image:"/static/images/7.png"},
            {title:"摇滚",image:"/static/images/8.png"},
        ],
        top:[
            {name:"歌名1",singer:"歌手1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:"时长1"},
            {name:"歌名2",singer:"歌手2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:"时长2"},
            {name:"歌名3",singer:"歌手3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:"时长3"},
            {name:"歌名4",singer:"歌手4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",time:"时长4"}
        ]
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
