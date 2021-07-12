<template>
    <div>
        <div v-for="item in items" :key="item.id">
            {{ item }}
        </div>
    </div>
</template>

<script>
    // 1.Vetur Vue文件内容高亮检查
    // 2.Vue VSCode Snippets快速生成模板代码
    export default {
        data() {
            return {
                key: value
            }
        },
        methods: {
            name() {
                
            }
        },
        computed: {
            name() {
                return this.data 
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>