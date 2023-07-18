<template>
    <div class="w-full flex flex-row bg-Grayish p-4">
        <!-- <LeftNav class="py-4 px-6 mr-4" /> -->
        <div class="w-9/12 flex flex-col justify-center items-center gap-8">
            <SearchBar class="w-2/4"/>
            <div class="w-full grid grid-cols-4 gap-8">
                <div v-for="p in products" :key="p.id">
                    <ProductCard :product="p" @add-to-cart="cartAdd"/>
                </div>
            </div>
        </div>
        <RightCart/>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const { data: products } = await useFetch('https://fakestoreapi.com/products/')
    let cart = [];
    let item = ref({
        id: 0,
        title: '',
        description: '',
        price: 0,
        category: '',
        image: '',
    })
    let cartAdd = (itemId) => {
        products.value = products.value.map((product) => {
            if (products.id === itemId) {
                item.value = {
                    id: products.id,
                    title: products.title,
                    description: products.description,
                    price: products.price,
                    category: products.category,
                    image: products.image,
                };
            }
        });
    }

    // const addToCart = (product) => {
    //     const existingItem = cartItems.value.find((item) => item.product.id === product.id);
    //     if (existingItem) {
    //     existingItem.quantity++;
    //     console.log(cartItems.value + "this one is added before");
    //     } else {
    //     cartItems.value.push({ product, quantity: 1 });
    //     console.log(cartItems.value + "this one is never added before");
    //     }
    // };
</script>

<style scoped>

</style>
