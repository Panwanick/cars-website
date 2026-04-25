<template>
  <div class="page">
    <!-- <h1>Product : {{ product }}</h1> -->
    <div class="card">
      <img :src="product.thumbnail" alt="Product Image" class="product-img">
      <div class="info">
        <h1 class="product-title">{{ product.title }}</h1>
        <h1 class="product-category">{{ product.category }}</h1>
        <h1 class="product-description">{{ product.description }}</h1>
        <h1 class="product-price">${{ product.price }}</h1>
      </div>
    </div>
  </div>
</template>

<script setup>

const route = useRoute();
const id_product = route.params.id_product;

// const ( params ) useRoute().params.id_product;
const { data: product } = await useFetch(`https://dummyjson.com/products/${id_product}`);
console.log('---------------');
console.log(product);
console.log('---------------');
</script>

<style scoped>
.page{
  max-width: 900px;
  margin: 40px auto;
  padding: 0 20px;
  font-family: sans-serif;
}
.card{
  display: flex;
  gap: 40px;
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  padding: 30px;
}
.product-img{
  width: 280px;
  height: 280px;
  object-fit: contain;
  flex-shrink: 0;
  border-radius: 8px;
  background: #f5f5f5;
}
.info{
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.product-title{
  font-size: 1.5em;
  font-weight: 700;
  color: #222;
  margin: 0;
}
.product-category{
  display: inline-block;
  background: #b06000;
  padding: 5px 12px;
  border-radius: 20px;
  font-size: 0.95em;
  font-weight: 600;
  text-transform: capitalize;
}
.product-description{
  color: #555;
  line-height: 1.2;
  font-size: 1.4em;
  margin: 0;
}
.product-price{
  font-size: 1.8em;
  font-weight: 700;
  color: #e67e00;
}
</style>