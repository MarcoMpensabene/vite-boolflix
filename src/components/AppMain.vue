<script>
import axios from "axios";
import MainFilmList from "./MainFilmList.vue"
import MainSearchFilm from "./MainSearchFilm.vue"
export default {
    components : {
        MainFilmList ,
        MainSearchFilm,
    },
    data() {
        return {
            filmsList : [] ,
            }
        },
        methods : {
        getFilms(input){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=391d0ce22ac893e9dbe22be6b0ef6c6a&query=' + input)
                .then( (response) => {
                    console.log(response.data.results);
                    console.log(this.userInput);
                    this.filmsList = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                });
        },
        searchFilms(userInput){
            this.getFilms(userInput);
        }
    },
}
</script>

<template>
    <main>
        <MainSearchFilm @filmsList="searchFilms" />
        <MainFilmList :filmsList="filmsList"/>
    </main>
</template>

<style scoped>

</style>
