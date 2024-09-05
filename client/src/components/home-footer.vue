<template>
    <footer>
        <button :style="styleButton" @click="showMenu">Поделиться</button>
        <ul :style="styleMenu">
            <li><a href="#"><img src="../assets/img/social/ok.svg" alt=""></a></li>
            <li><a href="#"><img src="../assets/img/social/tg.svg" alt=""></a></li>
            <li><a href="#"><img src="../assets/img/social/vk.svg" alt=""></a></li>
        </ul>
    </footer>
</template>

<script setup>
import { reactive } from 'vue';

    const styleMenu = reactive({
        display: 'none'
    })

    const styleButton = reactive({
        'border-radius': '10px 10px 0px 0px',
        'border-top': ''
    })
    
    function showMenu() {
        styleMenu.display = styleMenu.display === 'none' ? 'flex' : 'none'
        styleButton['border-radius'] = styleButton['border-radius'] === '10px 10px 0px 0px' ? '' : '10px 10px 0px 0px'
        styleButton['border-top'] = styleButton['border-top'] === '' ? '1px solid #0000001A' : ''
    }
</script>

<style scoped>
    footer {
        position: fixed;
        bottom: 0;
        margin-left: 80px;
    }

    button {
        background-color: #B54B62;
        color: #E5847B;
        padding: 6px 22px;
        font-size: 24px;
        position: relative;
        z-index: 2;
    }

    ul {
        border-radius: 10px 10px 0px 0px;
        background-color: #B54B62;
        justify-content: space-between;
        position: absolute;
        top: -40px;
        width: 100%;
    }

    li a {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 60px;
        height: 40px;
    }

    li a:hover {
        box-shadow: 0 0 5px #00000025 inset;
    }

    li:first-child a:hover {
        border-radius: 10px 0 0 0;
    }

    li:last-child a:hover {
        border-radius: 0 10px 0 0;
    }
</style>