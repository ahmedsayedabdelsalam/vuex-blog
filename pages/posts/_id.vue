<template>
    <div>
        <post :post="post" />
    </div>
</template>

<script>
import axios from 'axios'
import Post from '@/components/Post'

export default {
    data() {
        return {
            post: null
        }
    },
    components: {
        Post
    },
    asyncData({params}) {
        return axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
            .then(response => {
                return {
                    post: response.data
                }
            })
    },
}
</script>