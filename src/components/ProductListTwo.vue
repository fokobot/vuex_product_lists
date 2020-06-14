<template>
  <div class="productlisttwo">
    <h2>Product List Two</h2>
    <ul>
      <li v-for="product in saleProducts" v-bind:key="product.id">
        <span class="name">{{product.name}}</span>
        <span class="price">${{product.price}}</span>
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  computed: {
    products() {
      return this.$store.state.products;
    },
    saleProducts() {
      return this.$store.getters.saleProducts;
    }
  }
}
</script>

<style scoped>
.productlisttwo {
  background: #d1e4ff;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 30px;
  padding: 10px 20px;
}

.productlisttwo ul {
  padding: 0;
  list-style-type: none;
}

.productlisttwo li {
  margin-right: 10px;
  margin-top: 10px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.7);
}

.price {
  font-weight: bold;
  color: #860ce8;
  display: block;
}
</style>