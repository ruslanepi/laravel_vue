<template>
    <div>
        <router-view></router-view>
        <router-link to="/tags">tags</router-link>
        <router-link to="/posts">posts</router-link>
    </div>
</template>

<script>
export default {
    name: "Index"
}
</script>

<style scoped>

</style>
