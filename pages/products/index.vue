<script setup>
    const { data : products} = await useFetch('https://fakestoreapi.com/products')
</script>

<template lang="">
    <div class="nc-container nc-w-full nc-p-10 nc-h-full nc-grid nc-grid-cols-1 sm:nc-grid-cols-2 md:nc-grid-cols-3 lg:nc-grid-cols-4 nc-gap-5">
        <template v-for="(product, index) in products" :key="index">
            <nuxt-link :to="`/products/${product.id}`" class="nc-w-full nc-h-[350px] nc-border nc-shadow-md nc-p-2 nc-rounded-md">
                <div class='nc-h-[80%] nc-w-full nc-overflow-hidden'>
                    <img class="nc-h-full nc-w-full nc-object-contain nc-overflow-hidden hover:nc-scale-90 nc-scale-75 nc-transition-all nc-duration-500" :src="product.image" alt="">
                </div>
                <div class='nc-h-[20%] nc-w-full nc-border-t-2 nc-mt-2'>
                    <h1 class="nc-text-ellipsis nc-text-nowrap nc-overflow-hidden nc-cursor-pointer nc-text-gray-700 nc-font-bold nc-text-lg">{{product.title}}</h1>
                    <!-- <h2>{{product.description}}</h2> -->
                    <h2 class="nc-text-ellipsis nc-text-nowrap nc-overflow-hidden  nc-text-gray-500 nc-font-semibold nc-text-md">${{product.price}}</h2>
                </div>
            </nuxt-link>
        </template>
    </div>
</template>