<script >
export default {
    data() {
        return {
            userInput : "" ,
            }
        },
    }
</script>

<template>
    <div>
        <label for="title">Type films title</label>
        <input type="text" id="title-search" name="title-search" v-model="userInput" @keyup.enter="$emit('searchChannel' , userInput)">
        <button @click="$emit('searchChannel' , userInput)">PRESS</button>
    </div>
</template>

<style scoped lang="scss">

</style>
