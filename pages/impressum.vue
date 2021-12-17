<template>
    <div class="wrapper">
        <h1>Impressum</h1>
        <div class="impressumFlex">
            <h4>Konzept & Umsetzung</h4>
            <p>
                Nicole Bänninger, Simon Gisler, Mike Brechbühl und Levin Witjes
            </p>
            <h4>Adresse</h4>
            <p>6020 Emmenbrücke <br>
                Nylsuisseplatz 1</p>

            <h4>Kontakt</h4>
            <p>design-kunst@hslu.ch</p>

            <h4>Telefon</h4>
            <p>041 248 64 64</p>

            <h4>Copyright Bilder</h4>
            <p>Das Copyright der Bilder liegt beim Ringier Bildarchiv, Staatsarchiv Aargau.</p>
        </div>
    </div>
</template>

<script>
    export default {
        layout: 'noCover'
    }
</script>

<style scoped>
    .wrapper {
        max-width: 80vw;
        margin: 0 auto;
        padding: 6rem 0;
        min-height: 100vh;
    }

    .impressumFlex{
        width: 80vw;
        display: flex;
        flex-direction: column;
        margin-top: 8vh;
    }

    .impressumFlex h4{
        font-size: clamp(.6rem, 4vw, 3rem);
    }

    .impressumFlex p {
        margin-bottom: 2rem;
        width: 60%;
    }

</style>