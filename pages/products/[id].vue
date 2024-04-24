<template>
    <div>
        <Head>
            <Title>Cart | {{ product.title }}</Title>
            <Meta name="description" :content="product.description"/>
        </Head>
        <ProductDetails :product="product"/>
    </div>
</template>

<script setup>
// import { useFetch } from 'nuxt/app';

const { id } = useRoute().params;

const uri = 'https://fakestoreapi.com/products/' + id

const { data: product } = await useFetch(uri, {key : id})

if(!product.value) {
    throw createError({statusCode: 404, statusMessage: 'Produto não encontrado!', fatal: true})
}
definePageMeta({
    layout: 'products'
});

</script>
