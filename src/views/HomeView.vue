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
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.home {
  .feature-card {
    position: relative;

    .feratured-img {
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
}
</style>
