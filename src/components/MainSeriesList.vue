<script >
import axios from "axios";
import MainSingleSeries from "./MainSingleSeries.vue";
export default {
    components: {
        MainSingleSeries,
    },
    data() {
        return {
            
            }
        },
    props : {
        listSeries : {
            type : Array ,
            required : true ,
        }
    },
}
</script>

<template>
    <MainSingleSeries  v-for="serie in listSeries" :key="serie.id"  :listSeries="serie" />
</template>

<style scoped lang="scss">

</style>
