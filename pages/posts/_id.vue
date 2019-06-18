<template>
    <post :post="post" />
</template>

<script>
import axios from 'axios';
import Post from '@/components/Post.vue';

export default {
    data() {
        return {
            post: null
        }
    },
    async asyncData({ params }) {
        let response = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
        return {
            post: response.data
        }
    },
    components: {
        Post
    }
}
</script>
