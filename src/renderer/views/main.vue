<template>
    <div>
        <el-container class="container" id="main">
            <div ref="aside" class="aside">
                <div class="logo">
                    <div class="avatar no-drag">
                        <img src="../assets/images/logo.jpg">
                    </div>
                </div>

                <el-scrollbar class="menu-view scroll-page no-drag">
                    <div class="menu-group no-drag">
                        <img src="../assets/images/founder.png" alt="">
                    </div>

                    <div @click="articleListBtn" class="menu-group no-drag">
                        <img src="../assets/images/articleList.png" alt="">
                    </div>

                    <div class="menu-group no-drag">
                        <img src="../assets/images/folder.png" alt="">
                    </div>

                    <div class="menu-group no-drag">
                        <img src="../assets/images/recyleBin.png" alt="">
                    </div>
                </el-scrollbar>

                <div class="user-info  no-drag">
                    <div class="avatar no-drag" @click="login">
                        <img v-if="user.is_login" :src="user.profile.avatarUrl" />
                        <img v-else src="../assets/images/max.png">
                    </div>
                    <div class="mt-5">
                        <el-button style="color: #555;" type="text" class="no-drag" size="mini" @click="login">
                            {{user.is_login?user.profile.nickname:"立即登录"}}
                        </el-button>
                    </div>
                </div>
            </div>

            <div ref="article" class="article">
                <article-box ref="article"></article-box>
            </div>
               
            <!-- <div  class="article" style="-webkit-app-region: drag"> -->
                <!-- <article-list class="articleList"></article-list> -->
            <!-- </div> -->


            <div class="content">
                <top-bar></top-bar>
                <contentr-view></contentr-view>
            </div>
            

        </el-container>

        <login-view />
    </div>
</template>
<script>
    import AsideView from '../components/Aside/'
    import ArticleBox from '../components/Article/'
    import ArticleList from '../components/Article/articleList'  

    import ContentrView from '../components/Content/'
    import TopBar from '../components/Content/topBar'
    import LoginView from '../components/Login/'
import { setTimeout } from 'timers';

    export default {
        components: { AsideView, ArticleBox, ArticleList, ContentrView, LoginView, TopBar },
        data() {
            return {
                msgFormSon: 'article',
                isShow: false,
                flag: false,
                eleNode: '',
            }
        },
        computed: {
            user() {
                return this.$store.state.user
            }
        },
        watch: {
            isShow: function(val, oldVal) {
                console.log(val);
                // console.log(oldVal);
                /* if (val) {
                    this.msgFormSon = 'animArticle';
                } else {
                    this.msgFormSon = 'article';
                } */
            }
        },
        mounted() {
            this.eleNode = this.$refs.article.children[0].children[0].children[0].children[0]
        },
        methods: {
            getMsgFormSon(data){
                this.isShow = data
            },
            login() {
                if (this.user.is_login) {

                } else {
                    this.$bus.$emit('login')
                }
            },
            articleListBtn() {
                var self = this;
                if (!this.flag) {
                    this.flag = true;
                    // this.$refs.aside.style.width = '8%';
                    this.$refs.article.style.width = '26%';
                        self.eleNode.style.display = 'block';
                     setTimeout(() => {
                    }, 500);
                } else if(this.flag) {
                    this.flag = false;
                    // this.$refs.aside.style.width = '8%';
                    this.$refs.article.style.width = '0';
                    setTimeout(() => {
                        }, 200);
                        self.eleNode.style.display = 'none';
                }
            }
        },
    }
</script>
<style lang="scss" scoped>
    @import url('../assets/css/aside.css');
    .container {
        position: relative;
        height: 100vh;
        width: 100%;
    }
    .aside {
        width: 8%;
        height: 100%;
        display: flex;
        flex-direction: column;
        background: linear-gradient(to bottom, #efefef, #efefef);
    }

    .article {
        background: #ffffff;
        // width: 26%;
        width: 0;
        height: 100%;
        border-right: 2px solid #dfdfdf;
        transition: width 1.5s;
        z-index: 100;
    }
    /* .no-drag {
        -webkit-app-region: drag;
    } */
</style>
