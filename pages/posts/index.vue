<template>
    <ul class="posts">
        <li v-for="post, index in posts" :key="index">
            <nuxt-link :to="`/posts/${post.id}`">{{post.title}}</nuxt-link>
        </li>
    </ul>
</template>

<script>
    export default {
        data() {
            return {
                posts: []
            }
        },
        async created() {
            const response = await this.$axios.get('http://jsonplaceholder.typicode.com/posts', {
                params: {
                    _limit: 20
                }
            })
            this.posts = response.data
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

    .posts a {
        cursor:pointer;
    }
</style>
