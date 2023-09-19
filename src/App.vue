<script>
import axios from "axios";

export default {
  data() {
    return {
      greeting: '',
    }
  },
  methods: {
    async fetchGreeting() {
      try {
        const response = await axios.get('http://localhost:5000/api/greeting');
        this.greeting = response.data.message;
      } catch (error) {
        console.log("error fetching the greeting:", error);
      }
    }
  }
}
</script>

<template>
<div class="container-md">
  <div class="row justify-content-center mt-5">
    <div class="col-auto">
      <button @click="fetchGreeting" type="button" class="btn btn-secondary btn-sm">Get Greeting</button>
      <p class="mt-4">{{ greeting }}</p></div>
  </div>
</div>
</template>

<style scoped>

</style>
