<script>
import axios from "axios";
import MainFilmList from "./MainFilmList.vue"
export default {
    components : {
        MainFilmList ,
    },
    data() {
        return {
            filmsList : [] ,
            userInput : "" ,
            }
        },
        methods : {
        getFilms(){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=391d0ce22ac893e9dbe22be6b0ef6c6a&query=' + this.userInput)
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
    },
    created(){
        this.getFilms();
    }
}
</script>

<template>
    <!-- <MainFilmList /> -->
    <div>
        <label for="title">Type films title</label>
        <input type="text" id="title-search" name="title-search" v-model="userInput">
        <button @click="getFilms">PRESS</button>
    </div>

    <div >
        <ul>
            <li v-for="film in filmsList" :key="film.id">{{ film.title }}</li>
        </ul>
    </div>
</template>

<style scoped>

</style>
