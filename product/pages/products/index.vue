<template>
    <title>products</title>

    <span v-if="loading">Loading....</span>
    <div v-if="!loading">
       
        <thead >
            <tr class="flex justify-between">
                <th class="flex-grow py-2 ">
                    <td>id</td>
                </th>
                <th class="flex-grow px-60 py-2">
                    <td>name</td>
                </th>
                <th class="flex-grow py-2 px-60">
                    <td>price</td>
                </th>
            </tr>
        </thead>
        <p v-for="(item, index) in products" :key="item.id">

        <div :class="index" class="bg-red-100 gap-2 mb-2 p-2">
            <span>{{ item.id }}&nbsp; : &nbsp;</span> <span><NuxtLink :to="`/products/${item.id}`" class="hover:underline hover:text-red-600 hover:text-xl">{{ item.title }}</NuxtLink>:</span> <span class="text-red-500">{{ item.price }}</span>

        </div>
        </p>
        <div class="container">

        </div>
    </div>
</template>


<script setup>



let {loading} = true;
const {  data: products } = await useFetch('https://fakestoreapi.com/products');
loading = false;
if (!loading)
{
    console.log("hiii");
}
else {
    console.log("bye");
}



</script>