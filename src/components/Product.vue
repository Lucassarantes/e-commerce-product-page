<template>
    <section class="grid grid-cols-2 absolute top-60">
        <div class="grid mb-10">
            <div class="w-full flex justify-center items-center mb-10">
                <img class="rounded-[0.75rem] w-7/12  cursor-pointer" :src='require(`../assets/${this.image}`)' alt="">
            </div>
            <div class="flex gap-9 justify-center">
                <img class="w-[7rem] h-fit rounded-lg cursor-pointer imgs hover:opacity-75" src="../assets/image-product-1-thumbnail.jpg" alt="">
                <img class="w-[7rem] h-fit rounded-lg cursor-pointer imgs hover:opacity-75" src="../assets/image-product-4-thumbnail.jpg" alt="">
                <img class="w-[7rem] h-fit rounded-lg cursor-pointer imgs hover:opacity-75" src="../assets/image-product-2-thumbnail.jpg" alt="">
                <img class="w-[7rem] h-fit rounded-lg cursor-pointer imgs hover:opacity-75" src="../assets/image-product-3-thumbnail.jpg" alt="">
            </div>
        </div>
        <div class="flex mt-12">
            <div class="w-full">
                <p class="uppercase text-sm mb-5 text-orange-600 font-semibold tracking-wide text-left">sneaker company</p>
                <h1 class="font-bold text-left text-6xl text-black mb-10">Fall Limited Edition <br> Sneakers</h1>
                <p class="text-sm text-gray-400 text-left font-[550]">These low-profile sneakers are your perfect casual wear<br>
                    companion. Featuring a durable rubber outer sole, they'll<br>
                    withstand everything the weather can offer.
                </p>
                <p class="font-bold text-2xl text-black mt-5 text-left">${{ this.precoUnitario }}.00 <span class="bg-orange-100 text-orange-600 ml-2 text-xs p-1 rounded">50%</span></p>
                <p class="text-gray-400 text-xs line-through text-left mb-10">$250.00</p>
                <div class="flex">
                    <span class="flex bg-gray-100 w-fit rounded-lg mr-5 px-5">
                        <button class="p-4 items-center flex rounded-lg">
                            <img src="../assets/icon-minus.svg" alt="" />
                        </button>
                        <span class="font-bold p-4">{{ this.quantidade ? 0 : 0 }}</span>
                        <button
                            class="p-4 items-center flex"
                            @click="this.addQuantidade()"
                        >
                            <img src="../assets/icon-plus.svg" alt="">
                        </button>
                    </span>
                    <span class=" cursor-pointer bg-orange-500 text-white flex w-fit px-16 py-3 rounded-md font-semibold items-center"><img class="w-5 h-fit mr-3" src="../assets/icon-cart-white.svg" alt=""> Add to cart</span>
                </div>
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
        mounted() {
            const imagens = document.querySelectorAll(".imgs");
            imagens.forEach(imagem => {
                imagem.addEventListener("click", () => {
                    imagem.classList.toggle("border-2");
                    imagem.classList.toggle("border-orange-600");
                    imagem.classList.toggle("opacity-75");
                });
            });
        },
        methods: {
            alterarImagem() {
                this.image = "";
            },
            addQuantidade() {
                this.qtdProdutos++;
            }
        }
    }
</script>
