<template >
       <article class="movie-card">{{movie.title}}</article> 
</template>
<script>
export default {
    props: {
        movie: {
            type: Object,
            required: true,
            },
        },

};
</script>
<style>
    
</style>