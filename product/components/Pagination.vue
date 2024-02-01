<template #pagination>
    <div>
        <p>
            current page : {{ currentPage }}
        </p>

        <div class="flex  ml-96">
            <p v-for="(index) in totalPage" :key="index">
                <button class="text-red-500 ml-2 size-10 " v-on:click="handlePage(index)">{{ index }}</button> |
            </p>
        </div>

    </div>
</template>

<script setup>
import { defineProps, ref, getCurrentInstance } from 'vue'
const length = defineProps(['length']);
const totalPage = length.length / 10;
const inst = getCurrentInstance();
const currentPage = ref(1);

const handlePage = (index) => {
    currentPage.value = index;

    inst.emit('current', currentPage.value);
}

</script>