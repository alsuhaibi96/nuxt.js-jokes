<template>
 <div>

 <nuxt-link to="/jokes">Back</nuxt-link>
  <div class="joke-container">

    <small>    {{ $route.params.id }}</small>
    <hr>
    <p>{{ joke }}</p>
    
  </div>
  </div>

</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      joke: {},
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
      this.joke = res.data.joke;
      console.log(this.joke)
    } catch (error) {
      console.log(error);
    }
  },
};
</script>

<style>
.joke-container{
    margin: 10px;

}
</style>