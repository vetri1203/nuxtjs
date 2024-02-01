<template>
    <div>

        <span v-if="$loading">Loading</span>
        <div class="container" v-if="!$loading">

            <div class="title">
                <h1 class="text-3xl font-bold  text-center">{{ product.title }}</h1>
            </div>

            <div class="productImg ml-96 mt-16 mb-16">
                <img :src="product.image" class="h-60   border-spacing-2 border-red-500" alt="img loading">
            </div>
            <div class="description mb-8">
                <label for="" class="text-2xl">Description : </label> &nbsp;<span> {{ product.description }}</span> <br>
            </div>

            <div class="rating text-2xl">
                <label for="" class="text-2xl">Rating : </label> <span>{{ product.rating.rate }}</span>
            </div>

            <NuxtLink to="/products" style="margin-left: 500px;" class="bg-red-500 p-3 mt-2 text-center  rounded-lg">Go Back
            </NuxtLink>
        </div>
    </div>
</template>


<script setup>
let { $loading } = true;
const { id } = useRoute().params
const url = "https://fakestoreapi.com/products/" + id;
const { data: product } = await useFetch(url, { key: id })
$loading = false;

</script>