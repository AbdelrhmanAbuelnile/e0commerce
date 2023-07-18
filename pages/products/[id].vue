<template>
    <div>
        <ProductsDetials :product="product" />
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    console.log(id)
    const uri = 'https://fakestoreapi.com/products/' + id 

    //fetch the product 
    const { data: product } = await useFetch(uri )

</script>

<style scoped>

</style>