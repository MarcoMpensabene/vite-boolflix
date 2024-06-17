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
        <li>{{ listSeries.original_name }} </li>
        <li>{{ listSeries.name }} </li>
        <li><span class="lang-icon" :class="`lang-icon-${listSeries.original_language}`"></span></li>
        <li>{{ listSeries.vote_average }}</li>
    </ul>
</template>

<style scoped lang="scss">
@use '../styles/flags.scss';
.lang-icon {
    background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
}
</style>
