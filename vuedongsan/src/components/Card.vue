<template>
    <div>
        <img class='room-img' :src="a.image">
        <h4 @click="$emit('openModal', a.id)">{{ a.title }}</h4>
        <p>{{ a.content }}</p>
        <p>{{ a.price }}</p>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        a: Object,
    }
}
</script>

<style>

</style>