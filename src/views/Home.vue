<template>
  <div class="home">
    <PizzaHome :page="pageData"/>
  </div>
</template>

<script>
// @ is an alias to /src
import PizzaHome from '@/components/PizzaHome.vue'
import RawData from '../partials/orders.json'
import '../assets/styles/index.scss'
export default {
  name: 'Home',
  components: {
    PizzaHome
  },
  data () {
    const pageData = RawData
    return {
      pageData
    }
  }
}
</script>
