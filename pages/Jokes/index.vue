<template>
    <div id="jokes">
        <h2 class="joke-title">Jokes</h2>
        <search-jokes @search-text='searchText'></search-jokes>
        <div class="dad-jokes">
            <div  v-for="joke in jokes" :key='joke.joke'>
                <Joke :joke='joke.joke' :id='joke.id'></Joke>
            </div>
        </div>      
    </div>
</template>
<script>
import axios from "axios";
import SearchJokes from "../../components/Search.Jokes.vue"
import Joke from "../../components/Joke.vue"
export default {
     data(){
        return{
            jokes: [],
        }
    },
    components:{
        Joke,
        SearchJokes
    },
     async created(){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get("https://icanhazdadjoke.com/search", config)
            this.jokes = res.data.results;        

        } catch (err) {
            console.log(err);
        }

        
    },
    methods:{
        async searchText(text){
            const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

            try {
                const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
                this.jokes = res.data.results;  
           

            } catch (err) {
                console.log(err);
            }
        }
    },
     head(){
        return{

            title: 'Dad Jokes',
            meta: [{
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes.'
                }]
        }
     
    }
}
</script>
<style lang="scss">
    #jokes{
        padding: 3% 15%;     

        & h2{
            margin-bottom: 3rem;
            text-align: center;
            text-transform: uppercase;
            font-size: 3rem;
            letter-spacing: 1rem;
        }
    }

    .dad-jokes{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 1.5rem;
    }

</style>