<template>
    <div class="spaceTitleSum">
        <div class="spaceTitle" v-for="(item, index) in count" :key="index">
            <AddSelect></AddSelect>            
        </div>
        <el-row>
            <el-button @click="addSpace" class="addSpace">添加空间</el-button>
        </el-row>
    </div>
</template>

<script>
import AddSelect from './addSelect'

export default {
    data() {
        return {
            options: [
                {
                    value: '选项1',
                    label: '黄金糕'
                },
                {
                    value: '选项2',
                    label: '双皮奶'
                }
            ],
            value4: '',
            count : 0,
            //设备添加
            list : [
                {
                    id : 0,
                    count : 0
                },
                {
                    id : 1,
                    count : 1
                }
            ]
        }
    },
    computed: {
        
    },
    components: {
        AddSelect
    },
    mounted() {
        
    },
    methods: {
        addSpace (index) {
            this.count = this.$store.state.count;
            this.count++;
            this.$store.commit('get_spaceCount', this.count)
        }
    },
}
</script>

<style>
    .spaceTitleSum{
        
    }
    .el-input{
        border:1px solid #000;
    }
    .el-input__inner{
        border:none;
        color:#000;
    }
    .addClick{
        margin-top:20px;
        background: rgb(156, 123, 33);
        color:#fff;
    }
    .spaceTitle{
        border-bottom: 3px solid #000;
        padding-bottom: 20px;
        margin-bottom: 20px;
    }
    .addClick{
        margin-top:20px;
        background: rgb(97, 81, 8);
        color:#fff;
    }
    .addKong{
        display: inline-block;
        width: 100px;
    }
    .addKong input{
        font-size:12px;
        background: rgb(97, 81, 8);
        color:#fff;
    }
    .spaceTitle-input{
        width: 130px;
    }
    .addSelect-input{
        width: 130px;
    }
    .spaceTitle-cen, .addSelect{
        margin-top:20px;
    }
    .dilite{
        display: inline-block;
        width: 30px;
        height: 30px;
        border-radius:50%;
        text-align: center;
        line-height: 30px;
        color:#fff;
        margin-left:10px;
        background: rgb(180, 139, 5);
    }
</style>
