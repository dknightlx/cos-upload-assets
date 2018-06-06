<template>
    <div class="container">
        <div>上传图片到腾讯云（Beta）</div>
        <div>
            <el-upload ref="upload"
                action="/test/upload"
                list-type="picture"
                :auto-upload="false"
                :on-preview="handlePreview"
                :on-remove="handleRemove"
                :multiple="true"
                :file-list="fileList">
                <el-button type="primary" slot="trigger">选择文件（可多选）</el-button>
                <el-button type="success" @click="submitUpload">上传全部</el-button>
                <el-button type="danger" @click="clearAll">清空上传</el-button>
                <el-button type="info" @click="viewAll">所有上传</el-button>
            </el-upload>
        </div>
        <!-- <div class="">项目测试阶段，如遇上传未成功，请刷新重试。如多次未成功请联系网站管理员</div> -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            fileList: []
        };
    },
    methods: {
        submitUpload() {
            this.$refs.upload.submit();
        },
        handleRemove(file, fileList) {
            console.log(file, fileList);
        },
        handlePreview(file) {
            console.log(file);
        },
        clearAll() {
            this.fileList = [];
        },
        viewAll() {
            this.$message({
                message: '功能开发中，敬请期待'
            });
        }
    },
    mounted() {
        this.$notify({
            title: '提示',
            message: '项目测试阶段，如遇上传未成功，请刷新重试。如多次未成功请联系网站管理员',
            duration: 0,
            position: 'bottom-right'
        });
    }
};
</script>

<style lang="less" scoped>

</style>
