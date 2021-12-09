<template>
    <div class="post">
        <nuxt-link to="/">Back to overview</nuxt-link>
        <button @click="handleBack">Go back in history</button>
        <h1 class="text-xxl">{{post.title}}</h1>
        <div>{{post.body}}</div>
    </div>
</template>

<script>
export default {
    async asyncData({ params, $axios}) {
            const post = await $axios.$get(`http://jsonplaceholder.typicode.com/posts/${params.id}`)
            return { post }
    },
    methods: {
        handleBack() {
            this.router.go(-1)
        }
    },
}
</script>