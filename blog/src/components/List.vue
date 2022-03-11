<template>
    <div @click="$router.push(`/detail/${a.id}`)" class='listContainer' v-for="(a, i) in blogData" :key='i'>
        <h4>{{ a.title }}</h4>
        <p>{{ a.title }}</p>
        <small>{{ a.date }}</small> <br>
    </div>
</template>

<script>
export default {
    name: 'list',
    props: {
        blogData: Array,
    }
}
</script>

<style>
    .listContainer {
        margin-top: 20px;
    }
</style>