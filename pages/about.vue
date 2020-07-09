<template>
    <div id="about">
        <h1>About dad jokes.</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa veritatis reiciendis repudiandae a delectus minima minus quaerat saepe, velit sequi odit sed expedita totam! Doloremque explicabo modi totam quasi nulla.</p>
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
        padding: 3% 15%;
    }
</style>