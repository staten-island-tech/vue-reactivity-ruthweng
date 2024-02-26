<template>
  <div>
<h2>{{ cheese.name }}</h2>
<h3>${{ cheese.price }}</h3>
<img :src="cheese.img" alt="" />
<h3>{{ clicked }}</h3>
<button @click="increment">Click Me</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  cheese: Object,
});

//clicker logic
const clicked = ref(0);
function increment(){
  clicked.value++;
}

</script>

<style scoped>
img {
  width: 300px;
  height: 350px;

}


</style>