<template>
  <div class="home">
    Home
    <div class="feature-card">
      <router-link to="/movie/tt0409591">
        <img
          src="../assets/chiba.png"
          alt=""
          class="featured-img"
        />
        <div class="detail">
          <h3>Naruto</h3>
          <p>Description Goes here</p>
        </div>
      </router-link>
    </div>
    <form @submit.prevent='SearchMovies()' class="search-box">
      <input type="text" v-model="search" placeholder="Search..." />
      <button type="submit" value="Search">Search</button>
    </form>
    <div class="movies-list">Movies</div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const search = ref('');
    const movies = ref([]);
    const SearchMovies = () => {
      if (search.value != "") {
        console.log(search.value);
      }
    }

    return {
      search,
      movies,
      SearchMovies,
    };
  },
};
</script>

<style lang="scss">
.home {
  .feature-card {
    position: relative;

    .featured-img {
      display: block;
      width: 100%;
      height: 300px;
      object-fit: cover;
      z-index: 0;
    }

    .detail {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background-color: rgba(0, 0, 0, 0.5);
      padding: 16px;
      z-index: 1;

      h3 {
        color: #fff;
        font-size: 1.5rem;
        margin-bottom: 8px;
      }

      p {
        color: #fff;
        font-size: 1rem;
      }

    }
  }
  .search-box {
    display: flex;
    align-items: center;
    margin-bottom: 16px;

    input {
      flex: 1;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 4px;
      outline: none;
    }

    button {
      padding: 8px;
      border: none;
      border-radius: 4px;
      outline: none;
      background-color: #4caf50;
      color: #fff;
      cursor: pointer;
    }
  }
}


</style>
