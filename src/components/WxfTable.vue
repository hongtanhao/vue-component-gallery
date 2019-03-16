<template>
  <div>
    <table class="table-style" :style="tbodyStyle">
      <thead>
        <th :style="thHeight" v-for="(item, index) in data.tcols" :key="index">{{item.lable}}</th>
      </thead>
      <tbody>
        <tr v-for="(row, index) in data.trows" :key="index" :style="trHeight" class="table-tr">
          <td v-for="(col, index) in data.tcols" :key="index">{{row[col.name]}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'WxfTable',
  props: ['data'],
  data () {
    return {
    }
  },
  computed: {
    textJustify () {
      if (this.data.display.textAlign === 'center') {
        return 'text-align: center'
      } else if (this.data.display.textAlign === 'right') {
        return 'text-align: right'
      } else {
        return 'text-align: left'
      }
    },
    trHeight () {
      return this.data.display.rowHeight + 'px' + '; line-height:' + this.data.display.rowHeight + 'px;'
    },
    thHeight () {
      return this.data.display.rowHeight + 'px' + '; line-height:' + this.data.display.rowHeight + 'px;'
    },
    tbodyStyle () {
      return this.textJustify
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

table, td, th {
    border: 1px solid #eeeeee;
}
.table-style {
  width: 100%;
  border-collapse: collapse;
}
.table-tr:hover{
  background-color: #eeeeee;
}
</style>
