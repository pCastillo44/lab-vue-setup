<template>
  <div class="father">
    <h2> Touch me!</h2>
    <button @click="showCard">Show Card</button>
  </div>
  <br>
  <Card :show="show" @closeFromChild="removeCard">
  </Card>
</template>
<script setup>
import {ref} from 'vue';
import Card from "./components/Card.vue";
const show = ref(false);
console.log(show.value)
function showCard() {
  if (show.value == false) {
    show.value = true
  }
  console.log(show.value)
}
function removeCard(x) {
  console.log(x)
  if (show.value == true) {
    show.value = false
  }
  console.log(show.value)
}
</script>
<style>
.father {
  border-radius:5px;
  border:solid 3px blue;
  margin:5% 5%;
}
.son {
  border-radius:5px;
  border:solid 3px red;
  margin:5% 5%;
}
</style>