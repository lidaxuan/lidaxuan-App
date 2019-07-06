<template>
    <div class="logo">
        <div class="avatar no-drag">
            <img src="../../assets/images/logo.jpg">
        </div>
    </div>
</template>
<script>
    export default {
        methods: {
            login() {
                if (this.user.is_login) {

                } else {
                    this.$bus.$emit('login')
                }

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
</style>
