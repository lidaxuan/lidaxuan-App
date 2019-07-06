<template>
    <div class="wrap">
        <logo/>
        <menus/>
        <user-info/>
    </div>
</template>
<script>
import UserInfo from './UserInfo'
import menus from './menu'
import logo from './logo'
export default {
    components: {
        UserInfo,
        menus,
        logo
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
</style>
