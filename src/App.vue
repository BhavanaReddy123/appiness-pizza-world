<template>
  <div id="nav">
    <div class="logo">
      <img src="https://www.appinessworld.com/images/appiness-logo-small.png" title="logo">
    </div>
    <div class="top-menu">
      <router-link to="/" class="home">Home</router-link>
      <router-link to="/orders">Orders</router-link>
    </div>
  </div>
  <router-view/>
</template>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  #nav {
    display: flex;
    padding: 2rem;
    box-shadow: 0 8px 6px -6px #ccc;
    .logo {
      display: flex;
      justify-content: flex-start;
      align-items: flex-start;
      flex: 1 1 0;
    }
    a {
      font-size: 1.5rem;
      color: var(--text-font-color);
      font-weight: var(--normal-font-weight);
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
      &.home {
        padding-right: 2rem;
      }
    }
  }
</style>
