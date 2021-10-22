<template>
  <div class="title">
    <h1>Birthday Logger</h1>
    <div class="birthday-data-div">
      <h2>name:</h2>
      <h2>mm/dd</h2>
      <h2>days remaining</h2>
    </div>
    <button class="click-button" v-on:click= 'test'>Add B-day!</button>
  </div>
  
</template>



<style >
.title{
}
</style>

<script>
Vue.component("birthday-data", {


methods:{ 
  test() {
    console.log('clicked')
  }
}
}) 
</script>
