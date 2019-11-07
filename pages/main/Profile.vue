<template>
    <div>个人中心</div>
</template>

<script>
export default {
    data() {
        return {
            title: "个人中心"
        }
    },
    head() {
        return {
            title: this.title,
            link: [
                { hid: "profile",rel: 'icon', type: 'image/x-icon', href: '/profile.png' }
            ]
        }
    }
}
</script>