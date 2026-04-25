<template>
  <div class="container">
    <h1>Welcome to my App</h1>
    <p>This is the home page..</p>
    <img src="/images/picture.jpg" alt="Picture">
  </div>
</template>

<script setup>
useHead({
    title: 'Home - My App',
    meta: [
        {name: 'description', content: 'This is the home page of My App.'}
    ]
})
</script>

<style scoped>
.container{
    text-align: center;
    margin-top: 50px;
    max-width: 100%;
    max-height: 100%;
}
img{
    max-width: 100%;
    height: auto;
}
</style>