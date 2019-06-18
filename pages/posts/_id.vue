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
    async asyncData({ params, error }) {
        try {
            let response = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
            return {
                post: response.data
            }
        } catch (e) {
            error({
                statusCode: e.response.status,
                message: `This page couldn't be found`
            });
        }
    },
    components: {
        Post
    },
    head(){
        return {
            title: this.post.title
        }
    }
}
</script>
