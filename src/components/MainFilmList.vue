<script >
import MainSingleFilm from "./MainSingleFilm.vue"
export default {
    components: {
        MainSingleFilm,
    },
    data() {
        return {
            }
        },
    props : {
        filmsList : {
            type : Array, 
            required : true,
        }
    }
}
</script>

<template>
    <ul v-for="film in filmsList" :key="film.id">
            <li>{{ film.title }} </li>
            <li>{{ film.original_title }} </li>
            <li>{{film.original_language }}</li>
            <li>{{ film.vote_average }}</li>
    </ul>
</template>

<style scoped lang="scss">

</style>
