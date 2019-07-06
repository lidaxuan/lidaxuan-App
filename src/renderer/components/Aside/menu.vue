<template>
    <el-scrollbar class="menu-view scroll-page">
        <div class="menu-group">
            <img src="../../assets/images/founder.png" alt="">
        </div>

        <div class="menu-group">
            <img src="../../assets/images/articleList.png" alt="">
        </div>

        <div class="menu-group">
            <img src="../../assets/images/folder.png" alt="">
        </div>

        <div class="menu-group">
            <img src="../../assets/images/recyleBin.png" alt="">
        </div>

    </el-scrollbar>
</template>

<script>
    export default {

    }
</script>

<style lang="scss" scoped>
    .scroll-page {
        overflow: hidden;
         /deep/ .el-scrollbar__wrap {
            overflow: hidden !important;
            margin-bottom: 0 !important;
            margin-right: 0 !important;
        }
    }
    .menu-view{
        -webkit-app-region: drag;
        flex: 1;
        overflow: hidden;
        .menu-group{
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            img {
                cursor: pointer;
                width: 40px;
            }
        }

    }
</style>
