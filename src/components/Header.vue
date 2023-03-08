<template>
    <div class="grid grid-cols-2 mt-10">
        <div class="flex ml-20 border-light-gray pb-10">
            <img class="w-36 h-9 self-start" src="../assets/logo.svg" alt="Logo">
            <nav class="flex justify-between ml-10 self-start gap-x-10">
                <a href="http://">Collections</a>
                <a href="http://">Men</a>
                <a href="http://">Women</a>
                <a href="http://">About</a>
                <a href="http://">Contact</a>
            </nav>
        </div>
        <div class="flex justify-end space-bettwen mr-20 border-light-gray pb-10">
            <img 
                class="h-6 self-center absolute right-56 top-[3.25rem]"
                src="../assets/icon-cart.svg"
                alt="Carrinho de compras"
                @click.prevent="$event=>abrirFecharLista()"
            />
            <span 
                class="
                    absolute
                    right-[8.65rem]
                    top-11
                    rounded-full
                    bg-orange-500
                    w-4
                    h-fit
                    p-0
                    m-0
                    pt-0.5
                    text-white
                    text-xs
                    leading-tight
                    text-center
                    mr-20
                    l-10
                ">
                5
            </span>
            <DropList v-show="teste === 1" />
            <img class="h-12" src="../assets/image-avatar.png" alt="Perfil">
        </div>
        <hr id="hr-principal" />
    </div>
</template>

<script>
import DropList from "./DropList.vue";

export default {
    name: "Header",
    components: {
        DropList
    },
    data() {
        return {
            teste: 0
        }
    },
    methods: {
        abrirFecharLista() {
            if(this.teste === 0) {
                this.teste += 1;
            } else {
                this.teste -= 1;
            }
        }
    }
};

</script>

<style>
    #hr-principal {
        width: 90vw;
        margin-left: 5vw !important;
        position: absolute;
        top: 9vw;
    }
    .top-13 {
        top: 3.25rem
    }
</style>
