<template>
    <div class="grid grid-cols-2 mt-10">
        <div class="flex ml-20 border-light-gray pb-10">
            <img class="w-36 h-9 self-start" src="../assets/logo.svg" alt="Logo">
            <nav class="flex justify-between ml-10 self-start gap-x-10">
                <a href="http://" class="hover:border-b-2 hover:border-orange-500 pb-14">Collections</a>
                <a href="http://" class="hover:border-b-2 hover:border-orange-500 pb-14">Men</a>
                <a href="http://" class="hover:border-b-2 hover:border-orange-500 pb-14">Women</a>
                <a href="http://" class="hover:border-b-2 hover:border-orange-500 pb-14">About</a>
                <a href="http://" class="hover:border-b-2 hover:border-orange-500 pb-14">Contact</a>
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
                "
                v-show="this.totalItens > 0"    
            >
                {{ this.totalItens }}
            </span>
            <DropList v-show="this.dropDown" :item="this.item" :totalItens="this.totalItens" @clear="$emit('clear')" />
            <img class="h-12" src="../assets/image-avatar.png" alt="Perfil">
        </div>
    </div>
</template>

<script>
import DropList from "./DropList.vue";

export default {
    name: "Header",
    components: {
        DropList
    },
    props: {
        totalItens: Number,
        item: Object
    },
    data() {
        return {
            dropDown: false,
        }
    },
    methods: {
        abrirFecharLista() {
            if(this.dropDown === false) {
                this.dropDown = true;
            } else {
                this.dropDown = false;
            }
        },
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
