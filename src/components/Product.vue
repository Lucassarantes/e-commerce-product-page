<template>
    <section class="grid grid-cols-2">
        <div class="flex justify-center">
            <img class="rounded-[0.75rem] w-80" :src='require(`../assets/${this.image}`)' alt="">
        </div>
        <div class="flex items-center">
            <div class="w-full">
                <p class="uppercase text-xs text-orange-600 font-semibold tracking-wide text-left">sneaker company</p>
                <h1 class="font-bold text-left text-3xl text-black mb-5">Fall Limited Edition <br> Sneakers</h1>
                <p class="text-xs text-gray-500 text-left">These low-profile sneakers are your perfect casual wear<br>
                    companion. Featuring a durable rubber outer sole, they'll<br>
                    withstand everything the weather can offer.
                </p>
                <p class="font-bold text-2xl text-black mt-5 text-left">${{ this.precoUnitario }}.00 <span class="bg-orange-100 text-orange-600 ml-2 text-xs p-1 rounded">50%</span></p>
                <p class="text-gray-400 text-xs line-through text-left mb-10">$250.00</p>
                <span class="flex bg-gray-100 w-fit rounded-lg"><button class="p-4 items-center flex rounded-lg"><img src="../assets/icon-minus.svg" alt="" /></button><span class="font-bold p-4">{{ this.quantidade ? 0 : 0 }}</span><button class="p-4 items-center flex"><img src="../assets/icon-plus.svg" alt=""></button></span>
                <span class="bg-orange-500 text-white flex w-fit px-8 py-3 rounded-md font-semibold"><img class="w-4 h-fit" src="../assets/icon-cart-white.svg" alt=""> Add to cart</span>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: "Product",
        data() {
            return {
                qtdProdutos: 0,
                image: "image-product-1.jpg",
                precoUnitario: 125
            }
        },
        methods: {
            alterarImagem() {
                this.image = "";
            }
        }
    }
</script>
