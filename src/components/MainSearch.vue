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
    <div >
        <label  for="title">Type films title</label>
        <input  type="text" id="title-search" name="title-search" v-model="userInput" @keyup.enter="$emit('searchChannel' , userInput)">
        <button  @click="$emit('searchChannel' , userInput)">PRESS</button>
    </div>
</template>

<style scoped lang="scss">
input{
    margin: 0 1rem 0;
    width: 200px;
}
div{
    display: flex;
    justify-content: center;
}
label{
    text-transform: uppercase;
    color: red;
    padding-top: 10px;
    font-weight: bolder;
}
button {
    transition: all 0.5s;
    font-size: 17px;
    padding: 1ch 2ch;
    background-color: black;
    color: white;
    font-family: Roboto, sans-serif;
    border: none;
    border-radius: 2px;
    box-shadow: 2px 2px 0px hsl(0, 0%, 90%),
        4px 4px 0px hsl(0, 0%, 80%),
        6px 6px 0px hsl(0, 0%, 70%),
        8px 8px 0px hsl(0, 0%, 60%),
        10px 10px 0px hsl(0, 0%, 50%),
        12px 12px 0px hsl(0, 0%, 40%),
        14px 14px 0px hsl(0, 0%, 30%),
        16px 16px 0px hsl(0, 0%, 20%),
        18px 18px 0px hsl(0, 0%, 10%);
}

button:hover {
    background-color: hsl(0, 0%, 75%);
    color: red;
    box-shadow: none;
}
</style>
