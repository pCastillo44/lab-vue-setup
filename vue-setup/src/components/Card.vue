<template>
    <div class="son" v-if="show">
    <h2> Hello World</h2>
    <button @click="removeCard">Remove Card</button>
  </div>
</template>
<script setup>
import {ref} from 'vue'
const props = defineProps(["show"]);
const emits = defineEmits(["closeFromChild"]);
const beer = ref({
    id: 1,
    name: 'Pale Ale',
    price: 50
})
function removeCard() {
    emits('closeFromChild', beer.value)
}
</script>
<style>
</style>