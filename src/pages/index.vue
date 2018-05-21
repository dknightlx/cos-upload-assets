<template>
    <div class="container">
        <div>上传图片到腾讯云</div>
        <div>
            <div is="Upload" ref="upload"
                list-type="picture"></div>
            <button>选择文件（可多选）</button>
            <button>上传全部</button>
            <button>清空上传</button>
        </div>
    </div>
</template>

<script>
import Upload from 'element-ui/lib/upload';

export default {
    components: {
        Upload
    }
};
</script>

<style lang="less" scoped>

</style>
