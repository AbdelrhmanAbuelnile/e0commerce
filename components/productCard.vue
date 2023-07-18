<template>
    <div class="card  p-4 text-center">
        <div class="w-full bg-white rounded-lg py-10 max-h-44 h-full flex justify-center items-center">
            <img :src="product.image" :alt="product.description" class="thumb">
        </div>
        <div class="text-left">
            <NuxtLink :to="`products/${product.id}`">
                <p class="font-bold text-Dark m-4 truncate">{{ product.title }}</p>
            </NuxtLink>
            <p class="font-bold text-Tertiary m-4 truncate">{{ product.category }}</p>
        </div>
        <div class="flex flex-row justify-between items-center">
            <p class="font-bold text-Dark m-4 truncate">$ {{ product.price }}</p>
            <button @click="$emit('addToCart', item.id)" class="bg-black text-white text-2xl rounded-lg px-3 py-2 m-4 hover:text-Success duration-300">
                <Icon name="material-symbols:add-shopping-cart-outline-rounded" class=""/>
            </button>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    let item = ref({
        id: 0,
        title: '',
        description: '',
        price: 0,
        category: '',
        image: '',

    })
    // console.log(item.value.id);
    const { product } = defineProps(['product'])
    const emits = defineEmits(['addToCart']);
    emits('addToCart');
    const addToCart = () => {
        item.value = {
            id: product.id,
            title: product.title,
            description: product.description,
            price: product.price,
            category: product.category,
            image: product.image,
        }; 
        console.log(item.value);
    };
</script>






<style scoped>
    .thumb{
        max-height: 120px;
        max-width: 70%;
        margin: 0 auto;
    }
</style>