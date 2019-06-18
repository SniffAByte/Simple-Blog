<template>
    <div class="container">
        <h1>{{ error.statusCode }}</h1>
        <p>{{ error.message }}</p>
    </div>
</template>

<script>
export default {
    props: ['error'],
    head() {
        return {
            title: this.error.message
        }
    }
}
</script>
