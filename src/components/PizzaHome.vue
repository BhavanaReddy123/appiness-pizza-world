<template>
  <div class="pizza-wrap">
    <div class="pizza-wrap-inner">
      <div class="background">
        <h1>{{page.response.data.name}}</h1>
        <h3>{{page.response.data.sub_title}}</h3>
        <button class="btn-success" @click="goToMenu">Let's check orders!</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'PizzaHome',
  props: {
    page: Object
  },
  methods: {
    goToMenu () {
      window.location.href = '/orders/'
    }
  }
}
</script>
<style lang="scss" scoped>
  .pizza-wrap {
    .pizza-wrap-inner {
        background: url('../assets/pizza.jpg');
        background-repeat: no-repeat;
        height: 800px;
        padding: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
        h1 {
          max-width: 500px;
        }
        h3 {
          font-style: italic;
          color: #000000b8;
        }
        .background {
          background: var(--site-bg-color);
          opacity: 0.8;
          max-width: 60%;
          margin: 0 auto;
          padding: 3rem 5rem;
          text-align: center;
        }
    }
  }
  @media screen and (max-width: 768px) {
    .pizza-wrap {
      .pizza-wrap-inner {
        .background {
          max-width: 100%;
          padding: 3rem 2rem;
        }
      }
    }
  }
</style>
