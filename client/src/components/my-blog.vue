<template>
    <main>
        <h1>Блог</h1>
        <ul>
            <li v-for="product in products" :key="product.id">
                <h3>{{ product.title }}</h3>
                <p>{{ product.description }}</p>
                <p>Категория: <strong>{{ product.category }}</strong></p>
                <p>Цена: <strong>{{ product.price }} руб.</strong></p>
                <img :src=product.images[0]>
            </li>
        </ul>
    </main>
</template>

<style scoped>
    main {
        padding: 10px;
        background-color: #FECFB0;
    }

    ul {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        width: 940px;
        margin: 0 auto;
    }

    li {
        display: flex;
        flex-direction: column;
        gap: 10px;
        background-color: #B54B62;
        border-radius: 10px;
        color: wheat;
        width: 300px;
        padding: 10px;
    }

    img {
        height: 150px;
        object-fit: contain;
        align-self: end;
    }
</style>

<script setup>
    import { ref } from 'vue';

    fetch('https://dummyjson.com/products')
    .then(res => res.json())
    .then(data => {
        products.value = data.products
    })

    const products = ref([])

    console.log(products.value);
    
</script>