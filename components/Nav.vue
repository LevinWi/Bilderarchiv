<template>
    <nav>
        <ul>
            <li>
                <nuxt-link to="/">Home</nuxt-link>         
            <li>
                <nuxt-link to="/about">About</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/contact">Contact</nuxt-link>
            </li>
        </ul>
    </nav>
</template>

<style>
    nav ul{
        display: flex;
        justify-content: space-between;
    }
</style>