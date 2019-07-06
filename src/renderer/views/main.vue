<template>
    <div>
        <el-container class="container" id="main">

            <div width="180px" class="aside">
                <aside-view />
            </div>

            <div class="article" height="100%" style="-webkit-app-region: drag">
                <!-- <article-list-header /> -->
                <article-box height="50px"></article-box>
                <article-list class="articleList"></article-list>
            </div>

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

    export default {
        components: {
            AsideView,
            ArticleBox,
            ArticleList,
            ContentrView,
            LoginView,
            TopBar
        },
        data() {
            return {
                
            }
        },
        methods: {
            
        },
    }
</script>
<style lang="scss" scoped>
    .container {
        position: relative;
        height: 100vh;
    }
    .aside {
        position: absolute;
        z-index: 2;
        width: 8%;
        height: 100%;
        display: flex;
        flex-direction: column;
        background: linear-gradient(to bottom, #efefef, #efefef);
    }
    .article {
        background: #ffffff;
        width: 26%;
        height: 100%;
        border-right: 2px solid #dfdfdf;
        position: absolute;
        left: -18%;
        // left: 8%;
        top: 0;
    }
    .content {
        position: absolute;
        right: 0;
        top: 0;
        width: 100%;
        height: 100%;
        // margin-top: 50px;
    }
</style>
