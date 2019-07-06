<template>
    <div class="top">
        <div class="left">
            <el-button class="no-drag" size="mini" type="text" @click="back">
                <i class="btn el-icon-arrow-left"></i>
            </el-button>
        </div>
        
        <div class="right">
            <el-button @click="minimize" class="no-drag" size="mini" type="text">
                <i class="btn el-icon-minus"></i>
            </el-button>
            <el-button @click="close" class="no-drag hover-color" size="mini" type="text">
                <i class="btn el-icon-close"></i>
            </el-button>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            close() {
                this.$confirm('此操作将退出李大玄的APP, 是否继续?', '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                }).then(() => {
                    this.$electron.ipcRenderer.send('close')
                }).catch(() => {

                })
            },
            minimize() {
                this.$electron.ipcRenderer.send('minimize')
            },
            back() {
                if (this.$route.name !== 'music') {
                    this.$router.go(-1)
                }
            },
            advance() {
                this.$router.go(1)
            },
        },
    }
</script>

<style lang="scss" scoped>
    .top {
        -webkit-app-region: drag;
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 50px;
        padding: 0 10px;
    }
    .btn {
        font-size: 17px;
        color: #999;
    }
    .btn:hover {
        color: #31c27c;
    }
</style>
