<template>
    <div
        class="w-6/12 bg-white relative top-20 left-20 shadow-lg z-30"
    >
        <h6 class="text-left font-bold p-10">Cart</h6>
        <hr class="light-gray mb-10"/>
        <div v-show="this.item === null || this.item === ''">
            <p>Your cart is empty.</p>
        </div>
        <div class="flex pb-10" v-show="this.item !== null && this.item !== ''">
            <div class="w-1/5 mx-2">
                <img class="rounded" src="../assets/image-product-1-thumbnail.jpg" alt="">
            </div>
            <div class="w-3/5 self-center">
                <p>{{ this.item.nome }}</p>
                <p>${{ this.item.precoUnitario }}.00 x 3 <strong>${{ this.precoTotal }}.00</strong></p>
            </div>
            <button></button>
        </div>
    </div>
</template>

<script>

export default {
    name: "DropList",
    props: {
        item: Object
    },
    data() {
        return {
            precoTotal: 0
        }
    },
    created() {
        if(this.item !== null && this.item !== '') {
            this.calculaPrecoTotal();
        }
    },
    methods: {
        calculaPrecoTotal() {
            this.precoTotal = this.item.precoUnitario * 3;
        }
    }
}
</script>
