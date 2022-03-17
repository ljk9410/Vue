<template>
    <div>
        <Post v-for="(a,i) in postData" :key="i" :post="a" />
    </div>
</template>



<script>
import Post from './Post.vue';

export default {
    name: 'container',
    props: {
        postData: Array,
    },
    components: {
        Post,
    }
}
</script>



<style>

</style>