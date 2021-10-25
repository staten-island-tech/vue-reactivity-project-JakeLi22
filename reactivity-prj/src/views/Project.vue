<template>
  <div id="container">
    <h1>Birthday Logger</h1>
    <div class="birthday-data-div">
      <h2>name:</h2>
      <h2>mm/dd</h2>
      <h2>days remaining</h2>
    </div>
    <button class="click-button" v-on:click= 'addDiv'>Add B-day!</button>
  </div>
  
</template>



<style >

</style>

<script >


/* Vue.component('birthday-data-div', { 
  template:`  <div class="birthday-data-div">
      <h2>name:</h2>
      <h2>mm/dd</h2>
      <h2>days remaining</h2>
    </div>`
 }) */
var container = new Vue({
  el: "#container",

  methods: {
    addDiv() {
      
      
    },
  },
});
</script>
