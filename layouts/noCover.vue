<template>
    <main>
        <Navigation/>
        <nuxt/>
    </main>
</template>

<style scoped>
    main {
        cursor: initial
    }

    main *{
        cursor: initial
    }

    main * *{
        cursor: initial
    }

    .navigation { 
        cursor: pointer!important;
    }

    #menuToggle{
        cursor: pointer!important;
    }

    ::selection {
        background:darkred;
        color: white;
    }

    ::-moz-selection {
        background:darkred;
        color: white;
    }
</style>