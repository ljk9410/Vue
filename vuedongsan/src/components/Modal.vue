<template>
    <div class="black-bg" v-if='modalState === 1'>
        <div class="white-bg" >
            <img class='room-img' :src="rooms[userClicked].image">
            <h4>{{ rooms[userClicked].title }}</h4>
            <p>{{ rooms[userClicked].content }}</p>
            <!-- <input @input="month = $event.target.value"> -->
            <input v-model.number="month">
            <p> {{ month }}개월: {{ rooms[userClicked].price * month }}원</p>
            <button @click="$emit('closeModal')">닫기</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    data() {
        return {
            month: 1,
        }
    },
    watch: {
        month(a) {
            if (isNaN(a) == true) {
                alert('숫자만 입력하세요.');
                this.month = 1;
            }
        }
    },
    props: {
        rooms: Object,
        modalState: Number,
        userClicked: Number,
    },
    beforeUpdate() {
        if (this.month === 2) {
            alert('다른 숫자를 입력하세요');
            this.month = 1;
        }
    }
}
</script>

<style>

</style>