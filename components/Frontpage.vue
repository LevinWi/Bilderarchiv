<template>
    <div class="frontpage">
        <h1>Das isch d Frontpage</h1>
        <p>Hie isch zimli viu text. Scho kress he?</p>
    </div>
</template>

<style>
    .frontpage {
        height: 100vh;
        width: 100vw;
        position: relative;
        z-index: 300;
        background-color: rgb(22, 10, 3);
    }
    .frontpage p {
        font-size: clamp(1rem, 2vh, 2rem);
        color: lemonchiffon;
    }
</style>