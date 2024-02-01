<template>
    <title>products</title>

    <span v-if="loading">Loading....</span>
    <div v-if="!loading">

        <ProductPage :products="products" />

    </div>
</template>


<script setup>



let { loading } = true;
const { data: products } = await useFetch('https://fakestoreapi.com/products');
loading = false;




</script>