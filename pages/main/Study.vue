<template>
    <div>学习指南</div>
</template>

<script>
export default {
    data() {
        return {
            title: "学习指南"
        }
    },
    head() {
        return {
            title: this.title,
            link: [
                { hid: "study",rel: 'icon', type: 'image/x-icon', href: '/study.png' }
            ]
        }
    }
}
</script>