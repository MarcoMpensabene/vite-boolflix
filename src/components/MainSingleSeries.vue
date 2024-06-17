<script >
export default {
    data() {
        return {
            }
        },
    props : {
        listSeries : {
            type : Object, 
            required : true,
        }
    }
}
</script>

<template>
    <ul>
        <img v-if="listSeries.poster_path" :src="`https://image.tmdb.org/t/p/w342/${listSeries.poster_path}`" alt="">
        <img v-else src="https://ih0.redbubble.net/image.5218811881.3250/raf,360x360,075,t,fafafa:ca443f4786.jpg" alt="">
        <li>Title : {{ listSeries.original_name }} </li>
        <li>Original Title :{{ listSeries.name }} </li>
        <li>Original Langueage : <span class="lang-icon" :class="`lang-icon-${listSeries.original_language}`"></span></li>
        <li>Average Vote : {{parseInt(listSeries.vote_average/2)}}</li>
    </ul>
</template>

<style scoped lang="scss">
@use '../styles/flags.scss';
.lang-icon {
    background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
}
</style>
