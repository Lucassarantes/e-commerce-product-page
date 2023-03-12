<template>
    <div
        class="w-6/12 bg-white relative top-20 left-20 shadow-lg z-30"
    >
        <h6 class="text-left font-extrabold p-10">Cart</h6>
        <hr class="light-gray mb-10"/>
        <div class="pb-10" v-show="this.item === null || Object.keys(this.item).length === 0">
            <p>Your cart is empty.</p>
        </div>
        <div class="flex pb-10 flex-wrap" v-show="this.item !== null && this.item !== '' && Object.keys(this.item).length !== 0">
            <div class="w-1/5 mx-4">
                <img class="rounded" src="../assets/image-product-1-thumbnail.jpg" alt="">
            </div>
            <div class="w-3/5 self-center">
                <p class="text-left">{{ this.item.nome }}</p>
                <p class="text-left">${{ this.item.precoUnitario }}.00 x {{ this.totalItens }} <strong class="ml-2">${{ this.item.precoTotal }}.00</strong></p>
            </div>
            <div class="1/5 flex items-center">
                <img
                    class="cursor-pointer"
                    src="../assets/icon-delete.svg"
                    alt=""
                >
            </div>
            <button class="w-11/12 bg-orange-500 text-white rounded-lg py-3 mt-10 ml-3">checkout</button>
        </div>
        
    </div>
</template>

<script>

export default {
    name: "DropList",
    props: {
        item: Object,
        totalItens: Number
    },
    data() {
        return {
            precoTotal: 0
        }
    },
    created() {
        if(this.item !== null && this.item !== '') {
            this.calculaPrecoTotal();
            console.log(this.item);
        }
    },
    methods: {
        calculaPrecoTotal() {
            this.precoTotal = this.item.precoUnitario * this.totalItens;
        }
    }
}
</script>
