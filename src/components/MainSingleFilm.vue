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
        <li>{{filmsList.original_language }}</li>
        <li>{{ filmsList.vote_average }}</li>
    </ul>
</template>

<style scoped lang="scss">

</style>
