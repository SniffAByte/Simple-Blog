<template>
    <div>
        <p>{{ posts }}</p>   
    </div>    
</template>

<script>
import axios from 'axios';
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
    }
}
</script>

