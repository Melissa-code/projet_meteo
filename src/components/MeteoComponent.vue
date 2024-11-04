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
                console.log(this.api_code)
                
                if (event.key == "Enter") {
                    axios
                    .get(`${this.url_recherche}q=${this.requete}&units=metric&APPID=${this.api_code}&lang=fr`)
                    .then(reponse => {
                        console.log(reponse)
                        this.temps = reponse.data
                        console.log(this.temps)
                    })
                    this.requete = ""
                }
            }
        }
    }


</script>


<style>

    .texte-affichage {
        font-size: 24px;
        font-weight: 300;
        line-height: 1.2;
    }

</style>