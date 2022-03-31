<template>
  <div class="movie-detail">
    <h2>{{movie.Title}}</h2>
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

<style>

</style>
