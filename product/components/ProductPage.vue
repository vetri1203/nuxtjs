<template>
    <div>

        <div v-for="(product, index) in showProducts" :key="index">
            <div class="flex flex-col">
                <p class="img mt-5">
                    <img :src="product.image" class="h-60 border-spacing-2 border-red-500" alt="">
                </p>
                <span class="mb-1">{{ product.title }}</span>
                <span>${{ product.price }}</span>
                <NuxtLink class="bg-red-400 pt-1 pb-1 pr-2 pl-2 ml-5 w-12 mb-8 rounded-md" :to="`/products/${product.id}`">
                    View
                </NuxtLink>
                <hr />
            </div>
            <hr />
        </div>


        <Pagination v-on:current="currentPage" v-bind:length="data.length" />

        <!-- <Pagination v-on:current="currentPage" v-bind:length="data.length" /> -->
    </div>
</template>

<script setup>
import { defineProps, ref, watchEffect } from "vue";

const product = defineProps(["products"]);
const data = ref(product.products);
const pageNumber = ref(1);
const min = ref(0);
const max = ref(10);
const showProducts = ref(data._rawValue.slice(min.value, max.value));

const currentPage = (page) => {
    pageNumber.value = page;

    if (page !== 1) {
        min.value = (page - 1) * 10;
        max.value = page * 10;
    }
    else {
        min.value = 0;
        max.value = 9;
    }


};

watchEffect(() => {

    showProducts.value = data._rawValue.slice(min.value, max.value);
    console.log("hii", showProducts._rawValue);

});
</script>
