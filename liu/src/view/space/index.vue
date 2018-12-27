<template>
    <div class="space">
        <el-button type="text" @click="dialogVisible = true">点击打开 Dialog</el-button>
        <el-dialog
            title="编辑设备信息"
            :visible.sync="dialogVisible"
            width="70%"
            :before-close="handleClose">
            <!-- 内容组件 -->
            <SpaceTitle></SpaceTitle>
            <span slot="footer" class="dialog-footer">
                <el-button @click="dialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>
    </div>
</template>

<script>
import SpaceTitle from './child/spaceTitle'

export default {
    data() {
        return {
            dialogVisible: false
        };
    },
    components: {
        SpaceTitle
    },
    methods: {
        handleClose(done) {
            this.$confirm('确认关闭？')
            .then(_ => {
                done();
            })
            .catch(_ => {});
        }
    }
};
</script>

<style>
    .space{
        width: 100%;
        height: 100%;
    }
    .el-dialog__wrapper{
        width: 100%;
        height: 100%;
    }
    .el-dialog{
        width: 70%;
        height: 70%;
    }
    .el-dialog__body{
        padding: 20px 20px 10px;
    }
    .el-dialog{
        width: 100%;
        height: 100%;
        overflow-y: auto;
    }
    .el-dialog__footer{
        text-align: center;
    }
    .el-button--default{
        width: 100px;
        margin-right: 5px;
        border:1px solid rgb(119, 77, 8);
    }
    .el-button--primary{
        width: 100px;
        margin-left: 5px;
        border:1px solid rgb(119, 77, 8);
        background: rgb(119, 77, 8);
    }
</style>
