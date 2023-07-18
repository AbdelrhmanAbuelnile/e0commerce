<template>
    <nav class="flex flex-col justify-start items-start gap-4 bg-white rounded-md sticky">
        <a href="/" class="mr-1"><img src="../assets/imgs/logo.png" alt=""></a>
        <ul class="flex flex-col justify-center items-start gap-2">

            <li>
                <button @click="toggle" class="flex flex-row justify-between items-center gap-4">
                    <Icon name="material-symbols:menu-rounded" class="w-10 h-8"></Icon>
                    <!-- <p
                        v-if="checker"
                        class="font-semibold  text-lg text-Success hover:text-Accent duration-100"
                    >
                        Menu</p> -->
                </button>
            </li>
            <li>
                <NuxtLink to="/" class="flex flex-row justify-between items-center gap-4">
                    <Icon name="material-symbols:storefront-outline" class="w-10 h-8"></Icon>
                    <!-- <p
                        v-if="checker"
                        class="font-semibold  text-lg text-Success hover:text-Accent duration-100"
                    >
                        Store</p> -->
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="/cart" class="flex flex-row justify-between items-center gap-4">
                    <Icon name="material-symbols:shopping-bag-sharp" class="w-10 h-8"></Icon>
                    <!-- <p
                        v-if="checker"
                        class="font-semibold  text-lg text-Success hover:text-Accent duration-100"
                    >
                        Cart</p> -->
                </Nuxtlink>
            </li>

        </ul>
    </nav>
</template>

<script setup>
let  checker = ref(false)
let  toggle = () => {
    checker.value = !checker.value
    if(checker.value){
        document.querySelector('nav').classList.add('w-1/12')
        document.querySelector('Icon').classList.add('bg-black','rounded-md','p-2')

    }else {
        document.querySelector('nav').classList.remove('w-1/12')
        document.querySelector('Icon').classList.remove('bg-black','rounded-md','p-2')
    }
}
</script>

<style scoped>
    .router-link-exact-active{
        background-color: #000;
        border-radius: 6px;
        padding: 6px;
        color: #FFF;
    }
</style>