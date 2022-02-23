<template>
    <main>
        
            <div class="container">

                <div class="row row-cols-5 justify-center py-5">

                    <CardMusic 
                    v-for="(details, indice) in dischi" 
                    :key="indice" 
                    :details="details"
                    />

                </div>

            </div>
       
    </main>
</template>

<script>

// integro axios nel mio progetto partendo dalla copia presente in node_modules
const axios = require('axios');
import CardMusic from './partials/CardMusic.vue';

export default {
    name: 'MyMain',
    data() {
        return {
            // creo un oggetto di personaggi
            dischi: [],
            loadingInPorgress: true, 
        }
    },
    components: {
        CardMusic
    },
    methods: {
        // creo una funzione
        getMusic() {
            // richiesta axios al server remoto - inserisco url personaggi
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.dischi = response.data.response;
                this.loadingInPorgress = false;
            })
            .catch(function(error) {
                // errore
                console.log(error);
            })
        }
    },
    // chiama la funzione una volta creata azione
    created() {
        this.getMusic();
    }
}
</script>

<style scoped lang="scss">

main {
    background-color: #1e2d3b;
    min-height: calc(100vh - 80px);
}
</style>