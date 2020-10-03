<template>
  <div class="home">
    <OrdersRecieved :page="pageData"/>
  </div>
</template>

<script>
// @ is an alias to /src
import OrdersRecieved from '@/components/OrdersRecieved.vue'
import RawData from '../partials/orders.json'
export default {
  name: 'Orders',
  components: {
    OrdersRecieved
  },
  data () {
    const pageData = RawData
    return {
      pageData
    }
  }
}
</script>
