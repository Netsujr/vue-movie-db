<template>
  <div class="movie-detail">
    <h2>{{movie.Title}}</h2>
    <p>{{movie.Year}}</p>
    <p>{{movie.Runtime}}</p>
    <img :src="movie.Poster" :alt="movie.Title" class='featured-img'>
    <p>{{movie.Plot}}</p>
  </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import env from '@/env';

export default {
  setup () {
    const movie = ref({});
    const route = useRoute();

    onBeforeMount(() => {
      fetch(`https://omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`)
        .then(res => res.json())
        .then(data => {
          movie.value = data;
        });
    });

    return {
      movie,
      route
    };
  }

}
</script>

<style lang='scss'>
.movie-detail {
  padding: 1rem;
  /* border: 1px solid #ccc; */

  h2 {
    color: #333;
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }

  .featured-img {
    display: block;
    max-width: 200px;
    margin-bottom: 1rem;
  }

  p {
    color: #333;
    font-size: 1rem;
    line-height: 1.5rem;
  }
}

</style>
