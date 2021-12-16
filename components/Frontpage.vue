<template>
    <div class="frontpage">
        <img id="logo" @mouseenter="zoom" @mouseleave="shrink" :src="`/pics/logo-stadtmuseum.svg`">
        <div class="textwrapper">
            <p>Willkommen im Stadtmuseum Aarau. Entdecke unsere neueste Ausstellung vor Ort oder bekomme einen kleinen Einblick auf dieser Webseite. <br> <br>
            Entdecke die Bilder in dem du mit der Lupe über die Seite fährst.</p>
        </div>

        <div class="scrollsign"></div>
    </div>
</template>

<script>
export default {
    methods: {
        zoom() {
            var cover = document.getElementById('cover')
            console.log(cover.style.width)
            cover.style.width = 400 + 'vw'
            console.log(cover.style.width)
        },
        shrink() {
            var cover = document.getElementById('cover');
            cover.style.width = 300 + 'vw'
        }
    }
}
</script>

<style scoped>

.frontpage {
    height: 100vh;
    width: 100vw;
    position: relative;
    z-index: 300;
    padding: 2rem 2rem 0 2rem;
}

#logo {
    width: 6rem;
}

.textwrapper{
    position: absolute;
    top: 35vh;
    left: 20vw;
    width: 30vw;
}

p { 
    font-size: clamp(1rem, 1.5vw, 3rem);
    color: white;
}

.scrollsign { 
    position: absolute;
    top: 90vh;
    left: 50vw;
    height: 1px; 
    width: 0px;
}

.scrollsign::after { 
    content: '';
    width: 0.1vw;
    height: 0px;
    display: block;
    background: white;
    animation: border-dance 2s infinite ease;
}

@keyframes border-dance {
    0% {
        height: 0px;
    }

    30% {
        margin-top: 0;
        height: 4rem;
    }

    50% {
        margin-top: 4rem;
        height: 0px;
    }

    100% {
        margin-top: 4rem;
        height: 0px;
    }

}
</style>