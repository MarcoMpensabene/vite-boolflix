<script>
import axios from "axios";
import MainFilmList from "./MainFilmList.vue";
import MainSearch from "./MainSearch.vue";
import MainSeriesList from "./MainSeriesList.vue";
export default {
    components : {
        MainFilmList ,
        MainSearchFilm,
        MainSeriesList,
    },
    data() {
        return {
            filmsList : [] ,
            listSeries : [] ,
            }
        },
        methods : {
        getFilms(input){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=391d0ce22ac893e9dbe22be6b0ef6c6a&query=' + input)
                .then( (response) => {
                    console.log(response.data.results);
                    this.filmsList = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                })
        },
        getSeries(input){
            axios.get('https://api.themoviedb.org/3/search/tv?api_key=391d0ce22ac893e9dbe22be6b0ef6c6a&query=' + input)
                .then( (response) => {
                    console.log(response.data.results);
                    this.listSeries = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                })
        },
        search(userInput){
            this.getFilms(userInput);
            this.getSeries(userInput);
        }
    },
}
</script>

<template>
    <main>
        <MainSearchFilm @searchChannel="search" />
        <MainFilmList :filmsList="filmsList"/>
        <MainSeriesList :listSeries="listSeries"/>
    </main>
</template>

<style scoped>

</style>
