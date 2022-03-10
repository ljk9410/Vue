<template>
    <div class="discount">
        <h4>지금 결제하면 {{ sale }}% 할인</h4>
    </div>
</template>

<script>
export default {
    name: 'Discount',
    data() {
        return {
            sale: 30,
        }
    },
    mounted() {
        let down = setInterval(() => {
            this.sale--;
            if (this.sale == 0) clearInterval(down);
        }, 1000);

    }
}
</script>

<style>

</style>