<template>
    <div class="header-view" :style="{height: height}">
        <div class="left flex-c-l">
            <div class="search no-drag">
                <el-input class="input" size="mini" prefix-icon="el-icon-search" placeholder="搜索文章标题"></el-input>
            </div>
        </div>
    </div>
</template>

<script>
    const {BrowserWindow} = require('electron')
    export default {
        props: {
            height: {
                type: String,
                default: '40px'
            }
        },
        methods: {
            close() {
                this.$confirm('此操作将退出大玄笔记, 是否继续?', '提示', {
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
            refresh() {
                this.$bus.$emit('page-refresh', this.$route.name)
            }
        }
    }
</script>

<style lang="scss" scoped>
    .header-view {
        display: flex;
        align-items: center;
        justify-content: center;
        background: pink;
        /deep/ .left {
            .btn {
                font-size: 17px;
                color: #999;
            }
            .btn:hover {
                color: #31c27c;
            }
            .el-icon-refresh {
                color: #333;
            }
            .search {
                margin-left: 15px;
                width: 230px;
                .el-input__inner {
                    border: none;
                    border-radius: 30px;
                    background: #e9e9e9;
                    color: #8c8c8c;
                }
            }
            .el-input__inner:focus {
                background: #fff;
            }
        }
        .right {
            .btn {
                font-size: 17px;
                color: #333;
            }
            .btn:hover {
                color: #31c27c;
            }
        }
    }
</style>
