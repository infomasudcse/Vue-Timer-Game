<template>
  <p> Youe Score is {{ score }} ms</p>
  <h2>{{ rank }}</h2>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return {
            rank: null
        }
    },
    mounted(){
        if(this.score < 10){
            this.rank = 'Ninja Fingers'
        } else if(this.score < 20){
            this.rank = 'Swift hunt'
        }else{
            this.rank = 'Snail peace...'
        }

    }

}
</script>

<style>

</style>