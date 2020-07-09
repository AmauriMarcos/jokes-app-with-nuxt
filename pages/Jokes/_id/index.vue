<template>
    <div class="joke-id">
        <nuxt-link tag="button" to="/jokes">Return to jokes</nuxt-link>
        <p class="id">ID: {{$route.params.id}}</p>
        <div class="main-joke">
            {{idJoke.joke}}
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
    }

    button{
        border: none;
        border-radius: 3px;
        padding: .7rem 1rem;
        background-color: royalblue;
        font-weight: bold;

        &:hover{
            background-color: rgb(56, 84, 168);
        }
    }

    .id{
        font-size:3rem;
        padding: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
        
    }

    .main-joke{
         height: 10rem;
         border-radius: 3px;
         box-shadow: 3px 3px 7px rgba(0,0,0,.5);
         display: flex;
         justify-content: center;
         align-items: center;
         font-size: 1.5rem;
         padding: 3rem;
    }
</style>