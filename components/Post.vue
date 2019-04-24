<template>
    <div class="psot">
        <nuxt-link :to="{ name: 'posts-id', params: { id: post.id } }"><h1 class="post__title">{{ post.title }}</h1></nuxt-link>
        <p>{{ post.body }}</p>
    </div>
</template>

<script>
export default {
    props: {
        post: Object
    }
}
</script>

<style lang="scss">
    .post {
        margin-bottom: 40px;

        &__title {
            font-size: 3em;
        }
    }
</style>
