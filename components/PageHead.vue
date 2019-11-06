<template>
    <div class="head-layout">
        <p style="font-size: 20px;margin-left: 50px;">{{title}}</p>
    </div>
</template>

<script>
const props = {
    title: {
        type: String,
        default: "garyhu"
    }
}
export default {
    name: 'PageHead',
    props,
}
</script>

<style scoped>

.head-layout {
    box-shadow: 0 5px 15px -10px #C1C1C1;
    width: 100%;
    height: 100px;
    background: #F5F5F5;
    display: flex;
    flex-direction: row;
    align-items: center;
}

</style>