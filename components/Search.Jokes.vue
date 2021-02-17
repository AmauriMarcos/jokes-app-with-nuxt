<template>
    <div id="search">
        <form @submit.prevent="onSubmit">
            <input type="text" placeholder="Search jokes..." v-model="text">
            <button class="btn" type="submit">Search</button>
        </form>
    </div>
</template>
<script>
export default {
    name: 'SearchJokes',
    data(){
        return{
            text: ''
        }
    },
    methods: {
        onSubmit(){
            this.$emit('search-text', this.text);
            this.text = '..';
        }
    }
}
</script>
<style lang="scss">
    #search{
        margin: 3rem 0;
    }
    form{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    input{  
        padding: .7rem 1rem;
        width: 50%;
        border: 1px solid rgb(192, 190, 190);
        outline: none;
        
    }
    .btn{
        background-color: rgb(91, 129, 151);
        border-radius: none;    
        padding: .72rem 1rem;
        transform: translateX(-2rem);
          
    }
</style>