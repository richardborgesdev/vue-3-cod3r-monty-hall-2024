<script setup>
import { ref } from 'vue';
import GiftComp from './GiftComp.vue';

defineProps({
  number: Object,
  hasGift: Boolean,
});

const open = ref(false);
const selected = ref(false);
</script>

<template>
  <div class="door-area">
    <div class="door-frame">
      <GiftComp v-if="open && hasGift" />
    </div>
    <div class="door">
      <div class="number">
        {{ number }}
      </div>
      <div class="knob">

      </div>
    </div>
  </div>
</template>

<style>
:root {
  --door-border: 5px solid brown;
}

.door-area {
  position: relative;
  width: 200px;
  height: 310px;
  border-bottom: 10px solid #aaa;
  margin-bottom: 20px;
  font-size: 3rem;

  display: flex;
  justify-content: center;
}

.door-frame {
  position: absolute;
  height: 300px;
  width: 180px;

  border-left: var(--door-border);
  border-top: var(--door-border);
  border-right: var(--door-border);

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.door {
  position: absolute;
  top: 5px;
  height: 295px;
  width: 170px;
  background-color: chocolate;

  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
}

.door .knob {
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background-color: brown;
  align-self: flex-start;
  margin-top: 60px;
}
</style>
