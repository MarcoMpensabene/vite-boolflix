<script >
export default {
    data() {
        return {
            }
        },
    props : {
        filmsList : {
            type : Object, 
            required : true,
        }
    }
}
</script>

<template>
    <ul>
        <img v-if="filmsList.poster_path" :src="`https://image.tmdb.org/t/p/w342/${filmsList.poster_path}`" alt="">
        <img v-else src="https://ih0.redbubble.net/image.5218811881.3250/raf,360x360,075,t,fafafa:ca443f4786.jpg" alt="">
        <li>{{ filmsList.title }} </li>
        <li>{{ filmsList.original_title }} </li>
        <li><span class="lang-icon" :class="`lang-icon-${filmsList.original_language}`"></span></li>
        <li>{{ filmsList.vote_average }}</li>
    </ul>
</template>

<style scoped lang="scss">
@use '../styles/flags.scss';
.lang-icon {
    background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
}
</style>
