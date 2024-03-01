<template>
  <div class="container">
    <div  v-for="product in products" :key="product.id">
      <div>Name: {{ product.name }}</div>
      <div>Price: {{ product.price }}</div>
      <div>Formatted price: {{ formattedPrice(product.price) }}</div>
      <div v-if="product.available">Available</div>
      <div v-else>Out of stock</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductDetails",

  data() {
    return {
      price: "",
      products: [
        {
          id: 1,
          name: "Product1",
          price: 100,
          available: true,
        },
        {
          id: 2,
          name: "Product2",
          price: 99,
          available: false,
        },
        {
          id: 3,
          name: "Product3",
          price: 99.99,
          available: true,
        },
      ],
    };
  },
  computed: {
    formattedPrice() {
        return price => `${price}$`
    },
  },
};
</script>

<style lang="css" scoped>
.container {
    display: grid;
    gap: 1rem;
}
.container > div {
  margin: auto;
  padding: 0.5rem;
  width: 200px;
  display: grid;
  gap: 1rem;
  border: 1px solid black;
  box-shadow: 5px 5px 10px gray;
}
</style>
