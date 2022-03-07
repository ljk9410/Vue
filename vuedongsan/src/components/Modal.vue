<template>
    <div @click='$emit("closeModal")' class="black-bg" v-if='modalState === 1'>
        <div class="white-bg" >
            <img class='room-img' :src="rooms[userClicked].image">
            <h4>{{ rooms[userClicked].title }}</h4>
            <p>{{ rooms[userClicked].content }}</p>
            <p>가격: {{ rooms[userClicked].price }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    props: {
        rooms: Object,
        modalState: Number,
        userClicked: Number,
    },
    data() {
        return {

        }
    }
}
</script>

<style>

</style>