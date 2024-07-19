<script setup>
import GiftComp from './components/GiftComp.vue';
</script>

<template>
  <h1>
    Problema de Monty Hall
  </h1>
  <GiftComp />
</template>

<style>
* {
  box-sizing: border-box;
  font-family: 'Montserrat', sans-serif;
}

body {
  color: white;
  background: linear-gradient(to right, rgb(21, 153, 87), rgb(21, 87, 153));
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#app h1 {
  border: 1px solid black;
  background-color: #0004;
  padding: 20px;
  margin-bottom: 60px;
}
</style>
