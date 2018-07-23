<template>
  <div id="app">
    <div id='nav'>
      <h1 @click="showCreate">Create</h1>
      <h1 >Battle Bots</h1>
      <h1 @click="showCollection">Collection</h1>
    </div>
    <section v-if="create">
      <create :bots='bots' :showCollection='showCollection' ></create>
    </section>
    <section v-else>
      <collection :bots='bots'> </collection>
    </section>
  </div>
</template>

<script>
import Create from './Components/Create'
import Collection from './Components/Collection'

export default {
  components: {
    create:Create,
    collection:Collection
  },
  data(){
    return{
      bots: [],
      create: true
    }
  },
  methods:{
    showCreate(){
      this.create=true
    },
    showCollection(){
      this.create=false
    }
  }
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Black+Ops+One');
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #4dd9e5;
  height: 200vh;
  width: 100vw;
}

#nav{
  display: flex;
  justify-content: space-around;
  align-items: center;
  background: grey;
  color: whitesmoke;
  width: 100vw;
  height: 100px;
}

h1, h2 {
  font-weight: strong;
  font-family: 'Black Ops One', cursive;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
