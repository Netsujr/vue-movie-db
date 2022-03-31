<template>
  <header>
    <router-link to="/">
      <h1><span>Vue</span>Movies</h1>
    </router-link>
  </header>
  <main>
    <router-view />
  </main>
</template>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: "Roboto", sans-serif;

  &::selection {
    background: transparentize(#42b883, 0.5);
  }

  body {
    background: #fafafa;
  }

  a {
    text-decoration: none;
    color: #42b883;
  }

  header {
    background: #2c3d4e;
    padding: 1rem 3rem;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }

  h1 {
    font-size: 2.5em;
    color: #fff;
    font-weight: 400;
    span {
      color: #42b883;
      font-weight: 200;
    }
  }
}
</style>
