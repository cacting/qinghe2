<template>
  <div>
    <image style="height:200px" i-class="split" src="/static/images/bj1.jpg" />
    <i-panel title=" ">
      <view>
        <i-card i-class="split" v-for="item in top" :key="item" :extra="item.name" :thumb="item.img">
            <view slot="content">歌手{{item.singer}}</view>
            <view slot="footer">专辑{{item.album}}</view>
        </i-card>
      </view>
    </i-panel>
  </div>
</template>


<script>
export default {
  data () {
    return {
      top:[]
    }
  },

  onLoad (option){
    console.log(option.type)
    this.top = require('@/data/' + option.type + '.json')    
  },

  methods: {
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .split{
    margin-bottom:10pt;
}
</style>
