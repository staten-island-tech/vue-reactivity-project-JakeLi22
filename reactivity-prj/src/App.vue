<template>
  <div id="container">
    <h1 class="website-title">Battery Cells</h1>
    <div class="cell-options">
     
      <!-- 
        img
        list
        cell name  
        quantity 2 button with plus and minus
          v-on:click="name of the function"
        price


       -->
    </div>
<button class="cart-button">Add to Cart</button>
<!-- see cart
emit to add a number to the cart(#)
.value of the box and 
 -->
  </div>
</template>

<style>
.container{
  background-color:red;
}
</style>

<script>
export default {
data(){
  return {
    cellType: "lithium-ion", 
    seller: "panasonic",
    types: [
      {
        cellId: 1, 
        cellName: "", 
        details: ["mAh","V"],
        cellImage: "", 
        cellPrice:1, 
        
      },
      {
          cellId: 2, 
        cellName: "", 
        details: ["mAh","V"],
        cellImage: "", 
        cellPrice:2, 
        
      }
    ]
  }
},
  methods: {
    increaseQuantity(){
      //this.name of the element += 1
    }

}
}
</script>