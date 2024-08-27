<template>
    <header>
        <nav>
            <ul>
                <li><a href="#">Главная</a></li>
                <li><a href="#">Блог</a></li>
                <li><a href="#">Контакты</a></li>
            </ul>
        </nav>
    </header>
</template>

<style>
    header {
        width: 900px;
        margin: 0 auto;
        background-color: brown;
        color: wheat;
        padding-top: 10px;
        padding-bottom: 10px;
    }

    ul {
        display: flex;
        gap: 10px;
        list-style: none;
    }

    a {
        color: wheat;
        text-decoration: none;
    }
</style>