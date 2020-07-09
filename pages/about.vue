<template>
    <div id="about">
        <h1>About Dad Jokes.</h1>
        <p><span class="site">icanhazdadjoke.com</span> is the largest selection of dad jokes on the internet. Now supporting many different integrations to ensure you can access the dad jokes that you need wherever you are.</p>
    </div>
</template>
<script>
export default {
     head(){
        return{
            title: 'About Page || Dad Jokes',
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
    #about{
        padding: 3% 30%;
        height: 88vh;
        background: linear-gradient(to left, rgba(0,0,0,.8), rgba(73, 73, 73, 0.9)), url("https://data.whicdn.com/images/314901423/original.jpg?t=1530385918");
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        color: #fff;
        
        & h1{
            font-size: 3rem;
            align-self: flex-start;
        }

        .site{
            color: yellow;
            font-size: 1.3rem;
        }
        
    }
</style>