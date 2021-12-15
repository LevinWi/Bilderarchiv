<template>
    <div class="footer">
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/DSGVO">dsgvo</nuxt-link>
        <nuxt-link to="/impressum">Impressum</nuxt-link>
    </div>
</template>

<style scoped>
    .footer{
        max-width: 80vw;
        margin: 0 auto;
        display: flex;
        flex-direction: row;
    }

    .footer a{
        padding: 0 8rem 2rem 0;
        display: inline-block;
        font-size: 1.4vw;
        transition: all .3s ease;
    }

    .footer a::after{
        content: '';
        width: 0px;
        height: 1px;
        display: block;
        background: white;
        transition: .3s;
    }

    .footer a:hover::after{
        width: 100%;
    }  
</style>