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
<div class="quantity-div">
  <button v-on:click = 'decreaseQuantity'
  ref= 'test-1'
  class="quantity-subtract-button">-</button>
  <input class="quantityValue" type="number">
  <button v-on:click = 'increaseQuantity'
  class="quantity-add-button">+</button>
</div>
<!-- see cart
emit to add a number to the cart(#)
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
   // quantity: 
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
      const quantity= $ref.test-1
       this.$ref.test-1.value += 1;
      
      console.log('added');
    },
    decreaseQuantity(){
      //this.name of the element -= 1
    }

}
}
</script>