<template>
    <div>
        管理平台
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: "管理平台"
        }
    },
    head() {
        return {
            title: this.title,
            link: [
                { hid: "manage",rel: 'icon', type: 'image/x-icon', href: '/manage.png' }
            ]
        }
    }
}
</script>