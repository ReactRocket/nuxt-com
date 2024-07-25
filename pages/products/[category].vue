<script setup>
    const { category } = useRoute().params;
    definePageMeta({
        layout: 'products',
    })
</script>

<template>
    <h1 class="nc-text-3xl nc-font-bold nc-underline">Product Category is {{ category }}</h1>
</template>

<style  scoped>
    
</style>
