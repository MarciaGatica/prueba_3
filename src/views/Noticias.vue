<script>
import { ref } from 'vue'
import axios from 'axios';


const noticias = ref([]);



export default {
    data() {
        return {
            noticias: ref([])
        };
    },
    created() {
        this.obtenerNoticia();
    },
    methods: {
        obtenerNoticia() {
            axios
                .get('http://3.138.52.135:3000/news')
                .then(response => {
                    this.noticias = response.data.news;
                })
                .catch(error => {
                    console.error(error);
                });
        }
    }
};
</script>

<template>
    <h1 class="titulo">Noticias Ufro</h1>
    <div class="contenedor">
        <div v-for="(noti, index) in noticias" :key="index" class="card">

            <img :src="(noti.imageUrl)" class="card-img-top">
            <div class="card-body">

                <h5 class="card-title">{{ noti.title }}</h5>


                <RouterLink to="/detalle_noticia" style="text-decoration: none">Ver Detalle</RouterLink>


            </div>
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
.contenedor {
    width: 100%;
    height: auto;
    display: flex !important;
    flex-wrap: wrap;
    text-align: center;
}

.card {
    margin: 2%;
    width: 20%;
}
</style>
