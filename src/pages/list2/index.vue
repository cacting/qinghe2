<template>
  <div>
    <i-panel title="歌曲">
      <view>
        <i-card v-for="item in list" :key="item" i-class="split" :title="item.name" thumb="item.img">
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
      list:[]
    }
  },
  onLoad (option){
    this.list = require('@/data/' + option.type + '.json')
    console.log(this.list)
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
