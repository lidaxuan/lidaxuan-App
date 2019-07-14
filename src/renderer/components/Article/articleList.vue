<template>
    <div class="articleList no-drag">
        <ul >
            <li v-for="(item, i) in list" :key="i">
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
    export default {
        data() {
            return {
                list: [
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
                    {tit: '文章标题asdasasdasdasasdasd默认显示6个字', time: '2019/3/12', content: '所在地法规和阿斯达阿斯达阿斯蒂芬相关法规和的统一规范的双方各试大哥阿奥术大师大所多法人是DF阿萨德发生的噶的风格'},
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
    }
</script>

<style lang="scss" scoped>
    .articleList {
        height: 100%;
        background: rgb(251, 251, 251);
        ul {
            background-color: pink;
            height: 100%;
        }
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
</style>
