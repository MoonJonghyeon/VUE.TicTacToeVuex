<template>
    <tr>
        <td-component v-for="(cellData, index) in rowData" :key='index' :cell-data="cellData" :cell-index='index' :row-index='rowIndex'></td-component>
    </tr>
</template>

<script>
import TdComponent from './Tdcomponent'

export default {
    props: {
        rowData: Array,
        rowIndex: Number,
    },
    data() {
        return {
            parent: '내가 니 애비다',
        };
    },
    components: {
        TdComponent,
    },
    computed: {
        rowData() {
            return this.$store.state.tableData[this.rowIndex]
        }
    }
}
</script>