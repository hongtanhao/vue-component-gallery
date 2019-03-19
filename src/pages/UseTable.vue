<template>
    <div class="UseTable">
        <wxf-table style="height: 500px; width:100%;" :data="dataTable"></wxf-table>
        <wxf-sorter pos='center' style="position: relative"
          @prevPage="onPrev"
          @nextPage="onNext"
          @curPage="onCur">
        </wxf-sorter>
    </div>
</template>
<script>
/* eslint-disable */
    import WxfTable from './../components/WxfTable'
    import WxfSorter from './../components/WxfSorter'
    import TableHead from './table-head.json';
    import TableBody from './table-body.json';
    export default {
        name: 'UseTable',
        data() {
            return {
                dataTable: {
                    display: {
                        textAlign: 'center', // 表头文本排列样式
                        rowHeight: '40', // 行高
                        style: 'normal', // 表格风格
                        thHeight: '40'
                    },
                    tcols: TableHead,
                    trows: TableBody // 生产中通过接口拿（即查询数据库中记录）
                }
            }
        },
        methods: {},
        components: {WxfTable,WxfSorter}
    }
</script>