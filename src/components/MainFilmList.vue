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
    <MainSingleFilm  v-for="film in filmsList" :key="film.id" :filmsList="film" />
</template>

<style scoped lang="scss">

</style>
