<template>
    <div class="joke-id">
        <nuxt-link tag="button" to="/jokes">&larr; Back</nuxt-link>
        <div class="my-joke">        
            <h3>{{idJoke.joke}}</h3> 
            <p class="id">ID: {{$route.params.id}}</p>       
        </div> 
    </div>
</template>

<script>
import axios from 'axios';
export default {
    head(){
        return{
            title: 'Specific Joke.'
        }
    },
    data(){
        return{
            idJoke: {}
        }
    },
    async created(){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
            this.idJoke = res.data

        } catch (error) {
            console.log(error);
        }
    }
}
</script>

<style lang="scss">
    .joke-id{
        padding: 3% 15%;
         background: linear-gradient(to left, rgba(0,0,0,.8), rgba(73, 73, 73, 0.9)), url("https://files2.abingcdn.com/balkaneu.com/uploads/2019/10/21185528/thumbnail-4.jpg");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        height: 90vh;
        z-index: 1;
        position: relative;
    }

   /*  .my-joke{
        padding: 5rem;
        background-color: #fff;
    } */
    button{
        border: none;
        border-radius: 3px;
        padding: .7rem 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: royalblue;
        font-weight: bold;
        text-transform: uppercase;

        &:hover{
            background-color: rgb(56, 84, 168);
        }
    }

    .id{
        font-size:1.3rem;
        padding: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
        
    }

    .my-joke{
       /*   height: 10rem; */
         border-radius: 3px;
         box-shadow: 3px 3px 7px rgba(0,0,0,.5);
         display: flex;
         flex-direction: column;
         font-size: 1.5rem;
         padding: 3rem;
         z-index: 50;
         color: #fff;
         position: relative;
         background-color: rgba(0,0,0,.4);
    }
</style>