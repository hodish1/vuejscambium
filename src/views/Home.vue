<template>
  <HeaderComponent></HeaderComponent>
  <ProductsComponent :products="products"></ProductsComponent>
</template>

<script>
import HeaderComponent from "@/components/Header";
import ProductsComponent from "@/components/products";
const axios = require("axios").default;

export default {
  name: "App",
  components: {
    HeaderComponent,
    ProductsComponent,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    fetchProducts: async () => {},
  },
  async mounted() {
    try {
      const res = await axios.get("https://fakestoreapi.com/products");
      this.products = res ? res.data : [];
    } catch (err) {
      console.error("Oops something went wrong");
    }
  },
};
</script>
