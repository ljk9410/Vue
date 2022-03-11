<template>
    <div>
        <h4>{{ blogData[$route.params.id].title }}</h4>
        <p>{{ blogData[$route.params.id].content }}</p>
        <router-view></router-view>
    </div>
</template>

<script>
export default {
    name: 'detail',
    props: {
        blogData: Array,
    }
}
</script>

<style>

</style>