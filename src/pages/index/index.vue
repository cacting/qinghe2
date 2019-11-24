<template>
  <div>
    <i-grid i-class="no-border">
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/5.png" />
        </i-grid-icon>
        <i-grid-label>欧美</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/6.png" />
        </i-grid-icon>
        <i-grid-label>日韩</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/7.png" />
        </i-grid-icon>
        <i-grid-label>港台</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/8.png" />
        </i-grid-icon>
        <i-grid-label>大陆</i-grid-label>
    </i-grid-item>
</i-grid>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },

  methods: {
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
