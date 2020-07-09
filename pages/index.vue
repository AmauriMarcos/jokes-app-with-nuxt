<template>
    <div id="home">
      <h2 class="home-title">Welcome to the best corny dad jokes.</h2>
      <nuxt-link tag="button" to="/jokes">Get Started</nuxt-link>
    </div>
</template>

<script>
export default {
  
}
</script>

<style>
#home{
    padding: 3% 15%;
    height: 88vh;
    background: linear-gradient(to left, rgba(0,0,0,.8), rgba(73, 73, 73, 0.9)), url("https://i2-prod.mirror.co.uk/incoming/article20056036.ece/ALTERNATES/s1200b/1_UK_JOKER_VERT_ALT_2764x4096.jpg");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.home-title{
   font-size: 3rem;
   color: white;
   margin-bottom: 2rem;
}
</style>
