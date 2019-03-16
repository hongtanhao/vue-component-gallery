<template>
  <div>
    <div :style="sorterPos">
    <div>
      <span class="sorter-btn" @click="onPrevPage">上一页</span>or
      <span class="sorter-btn" @click="onNextPage">下一页</span>
    <span>跳到第</span>
    <span>
      <input style="width: 40px; height:25px;" type="number" v-model="currentPageNo" name="" id="" @blur="onCurPage">
      </span>
    <span>页</span>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'WxfTable',
  props: ['pos'],
  data () {
    return {
      currentPageNo: ''
    }
  },
  computed: {
    sorterPos () {
      if (this.pos === 'left') {
        return 'position:absolute;left: 10px;'
      } else if (this.pos === 'right') {
        return 'position:absolute;right: 10px;'
      } else {
        return ''
      }
    }
  },
  methods: {
    onPrevPage () {
      this.$emit('prevPage', this.currentPageNo)
    },
    onNextPage () {
      this.$emit('nextPage', this.currentPageNo)
    },
    onCurPage () {
      this.$emit('curPage', this.currentPageNo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sorter-btn {
  display: inline-block;
  height: 28px;
  line-height: 28px;
  width: 56px;
  border-radius:4px;
  color: #ffffff;
  background-color: #f78989;
  margin: 10px;
  font-size: 14px;
}
</style>
