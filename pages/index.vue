<template>
    <div>
        <bg-layout @go="goMain"></bg-layout>
    </div>
</template>

<script>
    import BgLayout from "../components/BGLayout"
    export default {
        components: {BgLayout},
        methods: {
          goMain() {
            setTimeout(() => {
              this.$router.push("/main")
            },1000)
          }
        },
    }
</script>

<style scoped>
</style>