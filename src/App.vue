<template>
  <div class="container">
    <!-- #3 must use the component-->
    <Myheader mytitle="Pet Dogs" 
      aboutpage ="Dog Breeds" />
    
    <Dogbox :dogs = "dogs"/>
    <About aboutme="About" />
    



  </div>
</template>
<script>



//import HelloWorld from './components/HelloWorld.vue'
// 1
import Myheader from './components/Myheader.vue'
import About from './components/About.vue'
// ----import Bookbox from './components/Bookbox.vue'
import Dogbox from './components/Dogbox.vue'


// data url: http://localhost:5555/books , this might be different for you
export default {
  name: 'App',
  components: {
    // 2 register the component 
    Myheader,
    Dogbox,
    About
  },

  data(){
    return {
      dogs: []
    }
  },
  methods: {
    // promises

      async fetchDogs(){
         const res= await fetch('https://pet-dogs.herokuapp.com/db.json')
         const data= await res.json()
          console.log(data)
         return data
      }

  },

  async created(){
    this.dogs = await this.fetchDogs()
  }
}
</script>










<style>




@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #304D6D;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
  background-color: #A7CCED;
}

div{
  margin-bottom: 0.5em;
}



</style>


