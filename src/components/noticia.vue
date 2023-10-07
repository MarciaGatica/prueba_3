<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios';

const props = defineProps({
  newsId: {
    type: String,
    required: true
  },
})

const imageUrl  = ref('');
const title = ref('');
const source = ref('');

onMounted(async () => {

});
</script>

<template>
  <div class="card" style="width: 18rem;">
  <img :src="imageUrl" class="card-img-top">
  <div class="card-body">
    <h5 class="card-title">{{ newsId }}</h5>

    <h5 class="card-title">{{ title }}</h5>
    <h5 class="card-title">{{ source }}</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a v-for="t in types" :key="t.slot" href="#" class="btn btn-primary">{{ t.type.name }}</a>
  </div>
</div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings {

  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>