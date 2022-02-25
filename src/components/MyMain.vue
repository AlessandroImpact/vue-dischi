<template>

<main>

    <div class="container">
                <!--qui va la select-->
    </div>

            <div class="container">

            
                <div class="row row-cols-5 py-5 justify-center">

                <MyLoading v-if="loadingprocessing"></MyLoading>

                <DiscoCard v-else v-for="details in filtredGenre" :details="details" :key="details.id"/>

                </div>


            </div>
       
</main>
  


</template>

<script>
import axios from "axios";
import DiscoCard from "./DiscoCard.vue";
import MyLoading from "./MyLoading.vue";

export default {
    name: 'MyMain',

     data() {
        return {
            // creo un oggetto con variabile per l'eventuale caricamento
            dischi: [],
            loadingprocessing: true,
            CambioGenere: ""
        }
    },
    components: {
        DiscoCard,
        MyLoading,
        //MySelect da completare
    },
    methods: {
        
        getMusic() {

            // richiesta axios 
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.dischi = response.data.response;
                this.loadingprocessing = false;
                
            })
            .catch(function(error) {
                // error
                console.log(error);
            })
        },
         //funzione cambio genere
        FaiCambio(text) {
            this.CambioGenere = text;
        }
    },

     computed: {
        filtredGenre() {
            if ((this.CambioGenere == "") || (this.CambioGenere == "all")) {

                return this.dischi;

            } else {
                return this.dischi.filter(item => {

                    return item.genre.toLowerCase().replaceAll('', '').includes(this.changeGenre.toLowerCase().replaceAll('', ''));
                })
            }
        }
    },
   
    created() {
        this.getMusic();
    }

}

</script>






<style scoped lang="scss">
@import '../style/general.scss';

main {
    background-color: #1E2D3B;
    min-height: calc(100vh - 100px);
}

</style>