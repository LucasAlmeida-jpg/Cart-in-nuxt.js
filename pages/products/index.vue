<template>
    <div class="grid  grid-cols-4 gap-5">
       <div v-for="p in products" :key="p.id">
        <ProductCard :product="p" />
        <!-- <NuxtLink :to="`/products/${p.id}`">{{ p.title }}</NuxtLink> -->
    </div>
    </div>
</template>

<script setup>
definePageMeta({
    layout: 'products'
})
const {data: products} = await useFetch('https://fakestoreapi.com/products')

useHead({
    title: 'Nuxt | Merch',
    meta: [
        {
            name: 'description', content: 'Nuxt 3 Merch'
        }
    ]
})
</script>

<style lang="scss" scoped>

</style>