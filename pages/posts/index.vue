<template>
    <div>    
        <p>posts</p>
        <div v-if="posts">
            <post v-for="(post, index) in posts" :key="index" :post="post"></post>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import Post from '@/components/Post'

export default {
    data() {
        return {
            posts: []
        }
    },
    components: {
        Post
    },
    asyncData() {
        return axios.get('https://jsonplaceholder.typicode.com/posts')
            .then(response => {
                return {
                    posts: response.data
                }
            })
    }
}
</script>