<template>
    <div>
        <header>
        <nav class="bg-red-500 pt-5 flex p-2 sticky top-0 z-50">
            <NuxtLink class="ml-5  p-2 x-0 hover:text-black hover: rounded-lg hover:bg-white" to="/">Home</NuxtLink>
            <NuxtLink class="ml-5  p-2 x-0 hover:text-black hover: rounded-lg hover:bg-white" to="/about">About</NuxtLink>
            <NuxtLink class="ml-5  p-2 x-0 hover:text-black hover: rounded-lg hover:bg-white" to="/products">Products</NuxtLink>
        </nav>
    </header>


        <div >
            <slot/>
        </div>
    </div>

    
</template>