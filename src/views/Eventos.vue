<script>
import { ref } from 'vue'
import axios from 'axios';


import Noticia from '../components/noticia.vue'

const eventos = ref([]);



export default {
    data() {
        return {
          eventos: ref([])
        };
    },
    created() {
        this.obtenerEvento();
    },
    methods: {
      obtenerEvento() {
            axios
                .get('http://3.138.52.135:3000/events')
                .then(response => {
                    this.eventos = response.data.events;
                })
                .catch(error => {
                    console.error(error);
                });
        }
    }
};
</script>

<template>

<h1 class="titulo ">Eventos UFRO</h1>

<div v-for="(eve, index) in eventos" :key="index" class="card">
        <div class="card-body">
            <h5 class="card-title">{{ eve.title }}</h5>
            <h5 class="card-fecha">Fecha: {{ eve.day }}/{{ eve.month }}/{{ eve.year }}</h5>
            <h5 class="card-link">Link: {{ eve.source }}</h5>


        </div>
    </div>

    <div>
    <RouterView />
  </div>
</template>



<style scoped>
.titulo{
    margin-top: 2%;
    margin-bottom: 3%;
    text-align: center;
}

.card{
    text-align: center;
  height: 50%;
  margin-left: 10%;
  margin-right: 10%;
  margin-top: 3%;
  color: #003A6C;
   background-color:aliceblue;
   border-color: #003A6C;
}
</style>
