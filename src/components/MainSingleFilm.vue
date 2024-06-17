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
