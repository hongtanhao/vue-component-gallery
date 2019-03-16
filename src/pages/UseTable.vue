<template>
    <div class="UseTable">
        <wxf-table style="height: 500px; width:100%;" :data="dataTable"></wxf-table>
    </div>
</template>
<script>
/* eslint-disable */
    import WxfTable from './../components/WxfTable'
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
                    tcols: [
                        {
                            name: 'order',
                            lable: '序号'
                        },
                        {
                            name: 'date',
                            lable: '时间'
                        }, {
                            name: 'name',
                            lable: '姓名'
                        }, {
                            name: 'address',
                            lable: '地址'
                        },
                        {
                            name: 'address',
                            lable: '地址'
                        },
                        {
                            name: 'phone',
                            lable: '电话'
                        }
                    ],
                    trows: [
                        {   order: 1,
                            date: '2016-05-02',
                            name: '王小虎',
                            address: '上海市普陀区金沙江路 1518 弄',
                            phone: '1253687989899'
                        }, {
                            order: 2,
                            date: '2016-05-04',
                            name: '王小虎',
                            address: '上海市普陀区金沙江路 1517 弄',
                            phone: '1253687989899'
                        }, {
                            order: 3,
                            date: '2016-05-01',
                            name: '王小虎',
                            address: '上海市普陀区金沙江路 1519 弄',
                            phone: '1253687989899',
                        }, {
                            order: 4,
                            date: '2016-05-03',
                            name: '王小虎',
                            address: '上海市普陀区金沙江路 1516 弄',
                            phone: '1253687989899'
                        }
                    ]
                }
            }
        },
        methods: {},
        components: {WxfTable}
    }
</script>