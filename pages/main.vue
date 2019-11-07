<template>
    <div style="display: flex;flex-direction: row;height: 100vh;overflow: hidden;width: 100%">
        <div class="left_ly">
            <div 
                v-for="(item,index) in tabs" :key="index" 
                :class="['tab-layout',item.isShow?'tab-active-layout':'tab-noactive-layout']"
                @click="showTab(index)"
            >
                {{item.label}}
            </div>
        </div>
        <div style="width: calc(100% - 200px)">
            <page-head :title="title"></page-head>
            <nuxt-child/>
        </div>
    </div>
</template>

<script>
    import PageHead from "../components/PageHead"
    export default {
        components: {PageHead},
        middleware: 'loggerPage',
        data() {
            return {
                tabList: [
                    {
                        label: "首页",
                        path: "/main",
                        isShow: true
                    },
                    {
                        label: "管理平台",
                        path: "/main/Manage",
                        isShow: false
                    },
                    {
                        label: "学习指南",
                        path: "/main/Study",
                        isShow: false
                    },
                    {
                        label: "个人中心",
                        path: "/main/Profile",
                        isShow: false
                    },
                ]
            }
        },
        mounted() {
            console.log("挂载")
            this.tabs.forEach(item => {
                if(this.$route.path === item.path) {
                    item.isShow = true;
                }else {
                    item.isShow = false;
                }
            })
        },
        computed: {
            tabs() {
                this.tabList.forEach(item => {
                    if(this.$route.path === item.path) {
                        item.isShow = true;
                    }else {
                        item.isShow = false;
                    }
                })

                return this.tabList;
            },
            title() {
                if(this.tabs){
                    let tab = this.tabs.find(item => {
                        return item.isShow;
                    });
                    return tab.label;
                }
                return "garyhu";
            }
        },
        methods: {
            showTab(index) {
                this.tabs.forEach(item => {
                    item.isShow = false;
                })
                this.tabs[index].isShow = true;
                let path = this.tabs[index].path;
                this.$router.replace(path)
            },
        },
    }
</script>

<style scoped>
.left_ly {
    width: 200px;
    height: 100vh;
    background: #380b01
}

.tab-layout {
    width: 100%;
    height: 80px;
    font-size: 18px;
    cursor: pointer;
    text-align: center;
    line-height: 80px;
}

.tab-layout:hover {
    background: #641402;
    color: #44AAF6
}

.tab-noactive-layout {
    color: #ffffff;
}

.tab-active-layout {
    background: #641402;
    color: #44AAF6
}
</style>