<template>
    <header class="header">
        <h1 class="title">Dad Jokes</h1>
        <ul>
            <li>
                <nuxt-link tag="a" to='/' exact-active-class="active">Home</nuxt-link>
            </li>
            <li>
                <nuxt-link tag="a" to='/jokes' exact-active-class="active">Jokes</nuxt-link>
            </li>
            <li>
                <nuxt-link tag="a" to='/about' exact-active-class="active">About</nuxt-link>
            </li>
        </ul>
    </header>
</template>
<script>

export default {
    name: 'AppHeader',
   
    head(){
        return{
            title: 'Welcome to Dad Jokes',
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
    .active::after{
        content: "";
        height: 2px;
        width: 100%;
        background-color: rgba(255,255,255,.4);
        display: block;
        transform: translateY(.5rem);
    }
    .header{
        display: flex;
        background-color: rgb(34, 31, 31);
        justify-content: space-around;
        align-items: center;
    
    }

    ul{
        display: flex;
        list-style: none;

        & li{
            padding: 1rem ;
            text-decoration: none;
            font-size: 1.3rem;        
        }

        & a{
            color: rgb(111, 139, 192);
            
            &:hover{
                color: rgb(180, 61, 61);
                text-decoration: none;
            }
        }
    }

    .title{
        color: #fff;
        text-transform: uppercase;
        letter-spacing: .5rem;
        font-family: 'Caveat', cursive;
    }
</style>