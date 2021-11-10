<template>
<div>
    <h1>Componente de peliculas</h1>
<section class="movie-grid">
    <movieCard :movie="movie"/>
</section>
</div>
</template>

<script>

import movieApi from '@/services/movieApi.js'
import movieCard from './movieCard.vue'
import Movie from '@/models/Movie.js'

export default {
    components: { movieCard },
    data() {
        return {
            movies: [],
        };
    },
    mounted() {
        this.getMovies();
    },
    methods: {
        async getMovies(){
            const {data} = await movieApi.getMovies();
            this.movies = await Promise.all(
                data.results.map((mov) => this.getMovies(mov.name))
             );
        },
        async getMovie(movieId){
            const {data} = await movieApi.getMovie(movieId);
            const movieData =  new Movie(data);
            return movieData;
            },
    },
};
</script>

<style >
    .movie-grid{
        padding: 1rem;
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        grid-auto-rows: 250px;
        gap: 1rem;
        }
</style>