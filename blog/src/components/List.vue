<template>
    <div class='listContainer' v-for="(a, i) in blogData" :key='i'>
        <h4>{{ a.title }}</h4>
        <p>{{ a.title }}</p>
        <small>{{ a.date}}</small> <br>
        <small>{{ a.number }}</small>
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