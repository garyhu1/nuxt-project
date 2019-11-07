<template>
    <div style="display: flex;flex-direction: row;height: 100vh;overflow: hidden;width: 100%">
        <div>首页</div>
    </div>
</template>

<script>
    export default {
        components: {},
        asyncData(context) {},
        head() {
            return {
                title: "首页",
            link: [
                { hid: "main",rel: 'icon', type: 'image/x-icon', href: '/main.png' }
            ]
            }
        },
    }
</script>

<style scoped>
.left_ly {
    width: 200px;
    height: 100vh;
    background: #380b01
}
</style>