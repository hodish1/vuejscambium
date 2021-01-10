<template>
  <div class="container">
    <div class="row">
      <Cart :selectedProducts="selectedProducts"></Cart>
    </div>
    <div class="row align-items-start">
      <template v-for="product in products" :key="product.id">
        <div class="card-wrapper col-12 col-md-6 col-lg-3 mb-3">
          <ProductComponent
            @onAddToCart="addToCart($event)"
            :product="product"
          ></ProductComponent>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import Cart from "./Cart.vue";
import ProductComponent from "./product";
export default {
  name: "ProductsComponent",
  props: ["products"],
  components: {
    ProductComponent,
    Cart,
  },
  data() {
    return {
      selectedProducts: [],
    };
  },
  methods: {
    addToCart(product) {
      this.selectedProducts.push(product);
    },
  },
};
</script>

<style>
.card-wrapper {
  height: 450px;
}
</style>
