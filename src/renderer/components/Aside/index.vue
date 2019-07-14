<template>
    <div class="wrap">
        <!-- <logo/>
        <menus/>
        <user-info/> -->
        <div class="logo">
            <div class="avatar no-drag">
                <img src="../../assets/images/logo.jpg">
            </div>
        </div>

        <el-scrollbar class="menu-view scroll-page">
            <div class="menu-group">
                <img src="../../assets/images/founder.png" alt="">
            </div>

            <div class="menu-group">
                <img @click="articleListBtn" src="../../assets/images/articleList.png" alt="">
            </div>

            <div class="menu-group">
                <img src="../../assets/images/folder.png" alt="">
            </div>

            <div class="menu-group">
                <img src="../../assets/images/recyleBin.png" alt="">
            </div>
        </el-scrollbar>

        <div class="user-info avatar no-drag">
            <div class="avatar no-drag" @click="login">
                <img v-if="user.is_login" :src="user.profile.avatarUrl" />
                <img v-else src="../../assets/images/max.png">
            </div>
            <div class="mt-5">
                <el-button style="color: #555;" type="text" class="no-drag" size="mini" @click="login">
                    {{user.is_login?user.profile.nickname:"立即登录"}}
                </el-button>
            </div>
        </div>
    </div>
</template>
<script>
/* import UserInfo from './UserInfo'
import menus from './menu'
import logo from './logo'
export default {
    components: {
        UserInfo,
        menus,
        logo
    }
} */
    export default {
        data() {
            return {
               className: 'animArticle',
               flag: false
            }
        },
        methods: {
            login() {
                if (this.user.is_login) {

                } else {
                    this.$bus.$emit('login')
                }
            },
            articleListBtn() {
                this.flag = !this.flag
                this.$emit('func', this.flag);
                /* if (this.flag) {
                    this.$emit('func', 'article');
                    this.flag = false;
                } else if(!this.flag) {
                    this.$emit('func', 'animArticle');
                    this.flag = true;
                } */
            }
        },
        computed: {
            user() {
                return this.$store.state.user
            }
        }
    }
</script>
<style lang="scss" scoped>
    .wrap{
        flex: 1;
        display: flex;flex-direction: column;
        border-right: 2px solid #dfdfdf;
    }
    .wrap /deep/ .el-scrollbar__wrap {
        overflow: hidden;
        margin-bottom: 0;
        margin-right: 0;
    }
    .logo {
        -webkit-app-region: drag;
        height: 160px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        .avatar {
            width: 50px;
            height: 50px;
            img {
                width: 100%;
                height: 100%;
                border-radius: 50%;
                cursor: pointer;
            }
        }
    }
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
        z-index: 100;
        .menu-group{
            cursor: pointer;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            img {
                -webkit-app-region: drag;
                cursor: pointer;
                width: 40px;
            }
        }
    }
    .user-info {
        -webkit-app-region: drag;
        height: 160px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        .avatar {
            width: 50px;
            height: 50px;
            img {
                width: 100%;
                height: 100%;
                border-radius: 50%;
                cursor: pointer;
            }
        }
        .type-icons {
            display: flex;
            justify-content: center;
            i {
                font-size: 22px;
                color: #999;
                margin-left: 8px;
            }
            i:first-child{
                margin-left: 0;
            }
        }
    }
</style>
