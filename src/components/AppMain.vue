<script>
import axios from "axios";
export default {
    data() {
        return {
            filmsList : []
            }
        },
        methods : {
        getFilms(){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=391d0ce22ac893e9dbe22be6b0ef6c6a&query=ciao')
                .then( (response) => {
                    console.log(response.data.results);
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
    <div >
        <ul>
            <li v-for="info in filmsList" :key="info.id">{{ info.title}}</li>
        </ul>
    </div>
</template>

<style scoped>

</style>
