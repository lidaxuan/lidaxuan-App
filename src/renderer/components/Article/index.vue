<template>
    <div class="header-view" >
        <div class="left flex-c-l">
            <div class="search no-drag">
                <!-- <i class="el-icon-search"></i> -->
                <!-- <el-input size="mini" v-model="value" placeholder="搜索文章标题"></el-input> -->
                <input class="ipt" type="text" v-model="value" placeholder="搜索文章标题">
            </div>
        </div>

        <ul  class="articleList no-drag">
            <li v-for="(item, i) in newList" :key="i">
                <div>
                    <p class="title">{{item.tit}}</p>
                    <span class="time">{{item.time}}</span>
                </div>
                <div class="content">{{item.content}}</div>
            </li>
        </ul>
    </div>
</template>

<script>
    const {BrowserWindow} = require('electron')
    export default {
        props: {
            height: {
                type: String,
            }
        },
        data() {
            return {
                value: '',
                newList: [],
                list: [
                    {tit: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'cccccccccccccccccccccccccccccccccc', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'ababababababababasbababababababababb', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'ddddddddddddddddddddddddddddddddddd', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'fffffffffffffffffffffffffffffffffffffff', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文ggggggggggggggggggggggggggggggggg', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: 'gggggggggggfgfgfgfgfgfgfgfgfgfgfg', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                ]
            }
        },
        created() {
            this.newList = this.list;
        },
        watch: {
            value: function(val) {
                if (val) {
                    this.newList = [];
                    this.list.forEach(ele => {
                        if (ele.tit.indexOf(val) > -1) {
                            console.log(ele);
                            this.newList.push(ele)
                        }
                    });
                } else {
                    this.newList = this.list;
                }
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
        background: pink;
        height: 100%;
        width: 100%;
        /deep/ .left {
            -webkit-app-region: drag;
            height: 50px;
            .search {
                padding: 0 15px;
                width: 100%;
                display: flex;
                align-items: center;
                .ipt {
                    border: none;
                    border-radius: 30px;
                    background: #e9e9e9;
                    color: #8c8c8c;
                    display: none;
                    height: 30px;
                    font-size: 14px;
                    width: 100%;
                    padding-left: 10px;
                }
            }
            .ipt:focus {
                background: #fff;
            }
        }
        .articleList {
            height: 100%;
            overflow-y: scroll;
            background: rgb(251, 251, 251);
            background-color: pink;
            width: 100%;
            
            li {
                background-color: #fff;
                margin-bottom: 10px;
                padding: 10px;
                height: 130px;
                .title {
                    width: 100%;
                    color: #292929;
                    margin-bottom: 3px;
                    white-space:nowrap;
                    overflow:hidden;
                    text-overflow:ellipsis;
                }
                .time {
                    font-size: 14px;
                    color: rgb(150, 148, 148);
                }
                .content {
                    height: 60%;
                    width: 95%;
                    overflow: hidden;
                    text-align: center;
                    text-overflow: ellipsis;
                    white-space: wrap;
                }
            }
        }
    }
       
</style>
