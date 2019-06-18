<template>
    <div>
        <post v-for="post in posts" :key="post.id" :post="post" />
    </div>    
</template>

<script>
import axios from 'axios';
import Post from '@/components/Post.vue';

export default {
    data() {
        return {
            posts: []
        }
    },
    async asyncData() {
        let res = await axios.get('https://jsonplaceholder.typicode.com/posts');
        return {
            posts: res.data
        }
    },
    components: {
        Post
    }
}
</script>

