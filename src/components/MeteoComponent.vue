<template>
    
    <div class="container">
        <!-- title -->
        <h1 class="my-4 text-center">Mon application météo</h1>

        <!-- form -->
        <div class="form-group mb-5">
            <label for="position">Entrez le nom d'une ville : </label>
            <input 
                type="text" 
                id="position"
                class="form-control mt-2"
                v-model="requete"
                v-on:keypress="goMeteo"
            >
        </div>

        <!-- result -->
        <div class="w-75 m-auto mt-5" v-if="temps">
            <!-- town -->
            <h3 class="text-center mb-3">Position (ville): {{ temps.name }}</h3>
            
            <!-- meteo infos -->
            <div class="card text-center p-5">
                <p class="texte-affichage">
                    Température : {{ temps.main.temp.toFixed() }}°C
                </p>
                <p class="texte-affichage">
                    Temps : {{ temps.weather[0].description }}
                </p>
            </div>
        </div>
    </div>

</template>


<script>
    // Ajax call API OpenWeatherMap 
    import axios from 'axios';

    export default {
        name: 'MeteoComponent',
        data: function() {
            return {
                requete:'',
                temps: undefined,
                api_code: process.env.VUE_APP_API_KEY,
                url_recherche: 'https://api.openweathermap.org/data/2.5/weather?', 
            }
        },
        methods: {
            goMeteo(event) {
                if (event.key == "Enter") {
                    axios
                    .get(`${this.url_recherche}q=${this.requete}&units=metric&APPID=${this.api_code}&lang=fr`)
                    .then(reponse => {
                        this.temps = reponse.data
                    })
                    this.requete = ""
                }
            }
        }
    }
</script>

<style>
    .body {
        background: #ffd89b;  /* cf. UI gradients.com fallback for old browsers */
        background: -webkit-linear-gradient(to right, #19547b, #ffd89b);  /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to right, #19547b, #ffd89b); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    }

    .texte-affichage {
        font-size: 24px;
        font-weight: 300;
        line-height: 1.2;
    }
</style>