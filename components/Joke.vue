<template>  
    <nuxt-link :to="'jokes/' + id">
        <div class="joke">
            <p>{{joke}} </p>
            <span>ID:{{id}}</span>
        </div>
    </nuxt-link> 
</template>

<script>

export default {
    name: "Joke",
    props: ['joke', 'id']
}
</script>

<style lang="scss">
 .joke{
        padding: 2rem;
        width: 100%;
        color: rgb(255, 255, 255);
        font-size: 1.3rem;
        height: 28rem;
        box-shadow: 4px 3px 8px rgba(110, 110, 110, 0.7);
        border-radius: 3px;
        background: linear-gradient(to left, rgba(0,0,0,.8), rgba(73, 73, 73, 0.9)), url("https://cambridgewords.files.wordpress.com/2019/11/funny.jpg");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
   
    }

    span{
        font-size: 1rem;
        font-weight: bold;
        color: rgb(144, 160, 209);
    }
</style>