<template>
  <div class="card">
    <img :src="product.image" class="card-img-top" :alt="product.title" />
    <div class="card-body d-flex flex-column justify-content-center align-items-center">
      <h5 class="card-title">{{ product.title }}</h5>
      <p class="card-text">
        <!-- {{ product.description }} -->
      </p>
      <p class="card-text">
        <small class="text-muted">Price {{ product.price }}$</small>
        <br>
        <button class="btn btn-primary">Buy Now</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductComponent",
  props: ["product"],
};
</script>

<style>

.card-img-top{
  height: 200px;
  object-fit: cover;
}

.card{
   height: 100%;
}
</style>
