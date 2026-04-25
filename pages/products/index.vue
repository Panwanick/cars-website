<template>
  <div>
    <!-- <h1>All Products</h1>
    <p>This is the products page.</p>
    <ul>
        <li v-for="all_item in data.products" :key="all_item.id">
            {{ all_item.title }}
        </li>
    </ul> -->
    <!-- ex 2 -->
     <div class="product-grid">
        <NuxtLink class="container" :to="`/products/${product.id}`" v-for="product in data.products" :key="product.id">
          <h2 class="title">{{ product.title }}</h2>
          <img class="img_tumbail" :src="product.thumbnail" alt="product">
          <p>{{ product.description }}</p>
          <p class="price">Price: {{ product.price }} $</p>
        </NuxtLink>
     </div>
  </div>
</template>

<script setup>
const { data: data } = await useFetch('https://dummyjson.com/products?limit=10');
// console.log('---------------');
// console.log(data);
// console.log('---------------');
</script>

<style scoped>
.product-grid{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  padding: 30px;
}
.container{
  background: #fff;
  padding: 15px;
  text-decoration: none;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  text-align: center;
  color: black;
}
.container:hover{
  background: #ffbf8e;
}
.title{
  text-align: center;
  font-size: 1.2em;
}
.price{
  font-size: 1.3em;
  text-align: left;
}
</style>