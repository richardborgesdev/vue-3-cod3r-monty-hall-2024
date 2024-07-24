<script setup>
import { ref } from 'vue';
import DoorComp from './components/DoorComp.vue';

let started = ref(false);
let doorsAmount = ref(3);
let selectedDoor = ref(null);
</script>

<template>
  <h1>
    Problema de Monty Hall
  </h1>
  <div class="form">
    <div v-if="!started">
      <label for="doorsAmount">
        Quantas portas?
      </label>
      <input type="text" id="doorsAmount" size="3" v-model.number="doorsAmount">
    </div>
    <div v-if="!started">
      <label for="selectedDoor">
        Qual a porta premiada?
      </label>
      <input type="text" id="selectedDoor" size="3" v-model.number="selectedDoor">
    </div>
    <button v-if="!started" @click="started = true">
      Iniciar
    </button>
    <button v-if="started" @click="started = false">
      Reiniciar
    </button>
  </div>
  <div class="doors" v-if="started">
    <div v-for="i in doorsAmount" :key="i">
      <DoorComp :number="i" :hasGift="i === selectedDoor" />
    </div>
  </div>
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

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}

.form,
.form input,
.form button {
  margin-bottom: 10px;
  font-size: 2rem;
}

.doors {
  align-self: stretch;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
