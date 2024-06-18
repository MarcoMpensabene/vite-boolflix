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
    },
    methods : {
        
    }
}
</script>

<template>

        <div class="wrapper">
            <div class="card">
                <img v-if="filmsList.poster_path" :src="`https://image.tmdb.org/t/p/w342/${filmsList.poster_path}`" alt="">
                <img v-else src="https://ih0.redbubble.net/image.5218811881.3250/raf,360x360,075,t,fafafa:ca443f4786.jpg" alt="">
                <div class="descriptions">
                    <h1> <span>Title : </span> {{ filmsList.title }}</h1>
                    <h2><span>Original Title : </span> {{ filmsList.original_title }}</h2>
                    <p><span> Original language - </span> <span class="lang-icon" :class="`lang-icon-${filmsList.original_language}`"></span></p>
                    <p>
                        <span>Average Vote - </span> {{Math.floor(filmsList.vote_average/2)}}
                        <div class="vote">
                            <font-awesome-icon :icon="['fa', 'star']" v-for="(star , index) in 5" :key="index" 
                            :class="{ active: index < Math.floor(filmsList.vote_average/2) }"  />
                        </div>
                    </p>
                </div>
            </div>
        </div>
</template>

<style scoped lang="scss">
@use '../styles/flags.scss';
.lang-icon {
    background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
}
div.wrapper{
    width: calc(100% / 5 - 1rem);
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    flex: wrap;
}
.card{
    flex: 1;
    flex-basis: 300px;
    flex-grow: 0;
    height: 440px;
    background: #fff;
    border: 2px solid #fff;
    box-shadow: 0px 4px 7px rgba(0,0,0,.5);
    cursor: pointer;
    transition: all .5s cubic-bezier(.8,.5,.2,1.4);
    overflow: hidden;
    position: relative;
}
.card img{
    width: 100%;
    height:100%;
    transition: all .5s cubic-bezier(.8,.5,.2,1.4);
}
.descriptions{
    position: absolute;
    top:0px;
    left:0px;
    background-color: rgba(255,255,255,.7);
    width:100%;
    height:100%;
    transition: all .7s ease-in-out;
    padding: 20px;
    box-sizing: border-box;
    clip-path: circle(0% at 100% 100%);
}
.card:hover .descriptions{
    left:0px;
    transition: all .7s ease-in-out;
    clip-path: circle(75%);
}
.card:hover{
    transition: all .5s cubic-bezier(.8,.5,.2,1.4);
    box-shadow: 0px 2px 3px rgba(0,0,0,.3);
    transform: scale(.97);
}
.card:hover img{
    transition: all .5s cubic-bezier(.8,.5,.2,1.4);
    transform: scale(1.6) rotate(20deg);
    filter: blur(3px);
}
.card h1{
    color: #df0707;
    letter-spacing: 1px;
    margin: 0px;
}
span{
    color: #6aa84f;
}
h1,
h2,
p{
    margin-bottom: 1.5rem;
}
.active{
    color: yellow;
}
</style>
