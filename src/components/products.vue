<template>
  <div class="container">
    <div class="row align-items-start">
      <template v-for="product in products" :key="product.id">
        <div class="card-wrapper col-12 col-md-6 col-lg-3 mb-3">
          <ProductComponent :product="product"></ProductComponent>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import ProductComponent from "./product";
export default {
  name: "ProductsComponent",
  props: ["products"],
  components: {
    ProductComponent,
  },
};
</script>

<style>
.card-wrapper{
  height: 450px;
}
</style>
