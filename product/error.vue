<template>
    <div>

        <div class=" flex flex-col flex-start text-center align-middle mt-60">
            <p style="color: blue; font-size: x-large;">
                <span>Error with status code :</span>
                <span class="text-red-500"> {{ error.statusCode }}</span>
                
            </p> <br>
            <p style="color: blue; font-size: x-large;">
                <span>Message :</span>
                <span class="text-red-500">{{ error.message }}</span>
                 </p>

        <NuxtLink to="/" style="font-size: xx-large;" class="text-red-500 underline ">Home</NuxtLink>

        </div>
 
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

const msg = defineProps(['error']);

</script>