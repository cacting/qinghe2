<template>
  <div>
    <i-grid i-class="no-border">
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/5.png" />
      </i-grid-icon>
      <i-grid-label>书香古韵</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/6.png" />
      </i-grid-icon>
      <i-grid-label>拼搏生活</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
          <image src="/static/images/7.png" />
      </i-grid-icon>
      <i-grid-label>腊八年味</i-grid-label>
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


