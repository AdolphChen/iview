<!--<template>-->
    <!--<div>-->
        <!--<Tree :data="baseData" :load-data="loadData" multiple></Tree>-->
        <!--<Button @click="handleAdd">add</Button>-->
        <!--<Button @click="handleUpdate">update</Button>-->
    <!--</div>-->
<!--</template>-->
<!--<script>-->
    <!--export default {-->
        <!--data () {-->
            <!--return {-->
                <!--baseData: [-->
                    <!--{-->
                        <!--expand: true,-->
                        <!--title: 'parent 1',-->
                        <!--children: [-->
                            <!--{-->
                                <!--title: 'parent 1-0',-->
                                <!--expand: false,-->
                                <!--children: [],-->
                                <!--loading: false-->
                            <!--},-->
                            <!--{-->
                                <!--title: 'parent 1-1',-->
                                <!--expand: true,-->
                                <!--checked: true,-->
                                <!--children: [-->
                                    <!--{-->
                                        <!--title: '<span style="color: red">leaf</span>',-->
                                        <!--render: (h) => {-->
                                            <!--return h('Button', {-->
                                                <!--props: {-->
                                                    <!--type: 'primary',-->
                                                    <!--size: 'small'-->
                                                <!--},-->
                                                <!--on: {-->
                                                    <!--click: ({target}) => {-->
                                                        <!--this.logger(target.textContent);-->
                                                    <!--}-->
                                                <!--}-->
                                            <!--}, 'I\'m a button!');-->
                                        <!--}-->
                                    <!--}-->
                                <!--]-->
                            <!--}-->
                        <!--]-->
                    <!--}-->
                <!--]-->
            <!--};-->
        <!--},-->
        <!--methods: {-->
            <!--handleAdd () {-->
                <!--this.baseData.push(-->
                    <!--{-->
                        <!--title: 'test name',-->
                        <!--checked: true-->
                    <!--}-->
                <!--);-->
            <!--},-->
            <!--handleUpdate () {-->
                <!--const child = this.baseData[0].children[0].children[1];-->
              <!--//  console.log(JSON.stringify(this.baseData), '\n', JSON.stringify(child));-->
                <!--if (!child) return this.$Message.error('Node is async and is not loaded yet');-->
                <!--else this.$set(child, 'checked', true);-->
            <!--},-->
            <!--logger (txt) {-->
                <!--console.log(txt);-->
            <!--},-->
            <!--loadData (item, callback) {-->
                <!--setTimeout(() => {-->
                    <!--callback([-->
                        <!--{-->
                            <!--title: 'children-1',-->
<!--//                            loading: false,-->
                            <!--children: []-->
                        <!--},-->
                        <!--{-->
                            <!--title: 'children-2',-->
<!--//                            loading: false,-->
                            <!--children: []-->
                        <!--}-->
                    <!--]);-->
                <!--}, 2000);-->
            <!--}-->
        <!--}-->
    <!--};-->
<!--</script>-->

<template>
    <Tree :data="data3" show-checkbox multiple></Tree>
</template>
<script>
    export default {
        data () {
            return {
                data3: [
                    {
                        title: 'parent 1',
                        expand: true,
                        selected: true,
                        children: [
                            {
                                title: 'parent 1-1',
                                expand: true,
                                disabled: true,
                                children: [
                                    {
                                        title: 'leaf 1-1-1',
                                        disabled: true
                                    },
                                    {
                                        title: 'leaf 1-1-2'
                                    }
                                ]
                            },
                            {
                                title: 'parent 1-2',
                                expand: true,
                                children: [
                                    {
                                        title: 'leaf 1-2-1',
                                        checked: true
                                    },
                                    {
                                        title: 'leaf 1-2-1'
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>
