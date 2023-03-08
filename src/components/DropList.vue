<template>
    <div
        class="w-6/12 bg-white relative top-20 left-20 shadow-lg z-30"
        v-show="!temItem"
    >
        <h6 class="text-left font-bold p-10">Cart</h6>
        <hr class="light-gray mb-10"/>
        <p>Your cart is empty.</p>

    </div>

    <div
        class="w-full bg-white relative top-20 left-20 shadow-lg z-30"
        v-show="temItem"
    >
        <h6 class="text-left font-bold p-10">Cart</h6>
        <hr class="light-gray mb-10"/>
    </div>
</template>

<script>
export default {
    name: "DropList",
}
</script>
