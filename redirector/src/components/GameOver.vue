<template>
  <div class="container d-flex flex-column justify-content-center align-items-center">
    <h1>GameOver</h1>
    <br>
    <h1>The victor is {{this.winner.name}}</h1>
    <br>
    <button class="btn btn-primary" v-on:click="home">Return Home</button>
  </div>
</template>

<script>
export default {
  name: 'GameOver',
  data () {
    return {
      winner:{},
      loser:{}
    }
  },
  mounted() {
    this.declareWiner()
  },
  methods: {
    home(){
      location.replace(" ")
    },
    declareWiner(){
      if (this.$route.params.currentPlayers.player1.hp === 0) {
        this.winner = this.$route.params.currentPlayers.player2
      }else if (this.$route.params.currentPlayers.player2.hp === 0) {
        this.loser = this.$route.params.currentPlayers.player1
      }

    }
  },
  props: ['user', 'playingGame'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  height: 100vh
}
</style>
