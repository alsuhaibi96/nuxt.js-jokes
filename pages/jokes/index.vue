<template>
   <div>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
   </div>
  
  </template>
  
  <script>
   import axios from "axios";
   import Joke from "../../components/Joke.vue"

  export default {
    components:{
        Joke
    },
    data(){
return {
    jokes:[]

}
    },
    async created(){
const config={
    headers:{
        Accept:"application/json"
    }
}

try{
    const res=await axios.get("https://icanhazdadjoke.com/search", config)
  this.jokes=res.data.results
}
catch(error){
    console.log(error)
}
},
    head() {
      return {
        title: "Jokes",
        meta: [
          {
            hid: "Description",
            name: "description",
            content: "These are the jokes",
          },
        ],
      };
    },
  };
  </script>
  
  <style>
  
  </style>