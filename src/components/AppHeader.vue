<script >
import HeaderSearchFilm from "./HeaderSearchFilm.vue";

export default {
    components :{
        HeaderSearchFilm,
    },
    data() {
        return {
            }
          }
}
</script>

<template>
   <!-- <HeaderSearchFilm />
   <div>
        <label for="title">Type films title</label>
        <input type="text" id="title-search" name="title-search" >
        <button @click="$emit(searchFilms)">PRESS</button>
    </div> -->

</template>

<style scoped lang="scss">
    input{
        margin : 0 1rem 0 ;
        width: 200px;
    }
</style>
