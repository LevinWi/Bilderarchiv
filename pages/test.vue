<template>
    <div class="images">
        <figure v-for="image,index in images" :key="index">
            <img :src="image.thumbnailUrl" :alt="image.title">
            <figcaption>{{index}}. {{image.title}}</figcaption>
        </figure>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                images: []
            }
        },
        async created() {
            const response = await this.$axios.get('http://jsonplaceholder.typicode.com/photos', {
                params: {
                    _limit: 120
                }
            })
            this.images = response.data
        },
    }
</script>

<style>
    .images img {
        transition: none;
        width: 10%;
        filter: none;
        opacity: 1;
        min-width: 10%;
    }

    .images figure {
        display: initial;
    }
</style>
