<template>
    <main>
            <div class="container">
                <MySelect @changeGenre="changeDone"/>
            </div>

            <div class="container">

                <div v-if="!loadingInPorgress" class="row row-cols-5 justify-center py-5">

                    <CardMusic 
                    v-for="details in filtredGenre" 
                    :key="details.id" 
                    :details="details"
                    />

                </div>
                
                <MyLoader v-else />

            </div>
       
    </main>
</template>

<script>

// integro axios nel mio progetto partendo dalla copia presente in node_modules
const axios = require('axios');
import CardMusic from './partials/CardMusic.vue';
import MyLoader from './partials/MyLoader.vue';
import MySelect from './partials/MySelect.vue';

export default {
    name: 'MyMain',
    data() {
        return {
            // creo un oggetto di personaggi
            dischi: [],
            loadingInPorgress: true,
            changeGenre: ""
        }
    },
    components: {
        CardMusic,
        MyLoader,
        MySelect
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
        },
        // funzione per effettuare il cambio genere 
        changeDone(text) {
            this.changeGenre = text;
        }
    },
    computed: {
        filtredGenre() {
            if ((this.changeGenre == "") || (this.changeGenre == "all")) {
                return this.dischi;
            } else {
                return this.dischi.filter(item => {
                    return item.genre.toLowerCase().replaceAll('', '').includes(this.changeGenre.toLowerCase().replaceAll('', ''));
                })
            }
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