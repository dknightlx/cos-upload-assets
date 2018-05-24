<template>
    <div class="container">
        <div>上传图片到腾讯云</div>
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
            </el-upload>
        </div>
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
        }
    }
};
</script>

<style lang="less" scoped>

</style>
