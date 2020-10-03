<template>
  <div class="orders-list-wrap">
    <div class="img-outer">
      <img src="../assets/pizza-cover.jpg" title="pizza cover">
    </div>
    <div class="orders-list-inner">
      <h2>Orders Recieved</h2>
      <div class="card-list" v-for="item in page.response.data.orders" :key="item.key">
        <p><strong>Customer Name:</strong> {{item.name}}</p>
        <div><strong>Item Names:</strong><p v-for="item in item.items_ordered" :key="item.key"> {{item}}</p></div>
        <p><strong>No. of Items<br/> ordered:</strong> {{item.num_of_items}}</p>
        <p><strong>Total Amount:</strong> {{item.total_amount}}</p>
        <div class="status-btn">
          <button type="button" class="btn-success" @click="toggle($event)">{{item.status}}</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'OrdersRecieved',
  props: {
    page: Object
  },
  data () {
    return {
    }
  },
  methods: {
    toggle (event) {
      console.log(event.target.innerHTML)
      if (event.target.innerHTML === 'Order Received') {
        event.target.innerHTML = 'Preparing'
      } else if (event.target.innerHTML === 'Preparing') {
        event.target.innerHTML = 'Ready To Serve'
      }
    }
  }
}
</script>
<style lang="scss" scoped>
  .orders-list-wrap {
    display: flex;
    .orders-list-inner {
      overflow-y: scroll;
      height: 700px;
      display: inline-block;
    }
    .img-outer, .orders-list-inner {
      width: 48%;
      h2 {
        color: var(--btn-success-color);
        font-weight: var(--bold-font-weight);
      }
      .card-list {
        text-align: left;
        background: var(--card-bg-color);
        padding: 2rem;
        width: 450px;
        margin: 0 auto;
        margin-bottom: 2rem;
        .status-btn {
          .btn-success {
            min-width: 170px;
          }
          span {
            margin-left: 0.7rem;
            font-style: italic;
            font-weight: var(--bold-font-weight);
          }
        }
        p, div {
          font-weight: var(--medium-font-weight);
          font-size: 1.2rem;
          margin: 10px 0;
          strong {
            color: #00adca;
            min-width: 175px;
            display: inline-block;
          }
        }
      }
    }
  }
  @media screen and (max-width: 768px) {
    .orders-list-wrap {
      display: initial;
      .img-outer, .orders-list-inner {
          width: initial;
      }
    }
  }
</style>
