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
<button v-on:click = 'addToCart' class = "cart-button">Add to Cart</button>
    <div class="quantity-div">
      <button v-on:click = 'decreaseQuantity'
      class="quantity-subtract-button">-</button>
      <input v-model='numberQuantity'
      class="quantityValue" type="number">
      <button v-on:click = 'increaseQuantity'
      class="quantity-add-button">+</button>
    </div>
<!-- see cart
emit to add a number to the cart(#)
 -->
  </div>
</template>

<style>

</style>

<script>
export default {
data(){
  return {
    cellType: "lithium-ion", 
    seller: "panasonic",
    numberQuantity: '',
    types: [
      {
        cellId: 1, 
        cellName: "cell A", 
        details: ["mAh","V"],
        cellImage: "", 
        cellPrice:1, 
        
      },
      {
          cellId: 2, 
        cellName: "cell B", 
        details: ["mAh","V"],
        cellImage: "", 
        cellPrice:2, 
        
      }
    ]
  }
},
  methods: {
      decreaseQuantity(){
      const returnedNumber = parseInt(this.numberQuantity,10);
      console.log('subtracted');
      const subtracted = this.numberQuantity =  returnedNumber-1;
      console.log(subtracted);
    },

    increaseQuantity(){
      const returnedNumber = parseInt(this.numberQuantity,10);
      console.log('added');
      const increased = this.numberQuantity =  returnedNumber+1;
      console.log(increased);
    },

    addToCart(){
      const inputBoxValue = parseInt(this.numberQuantity,10);
      console.log(inputBoxValue);

    },  
    
    priceCalculator(){
      // const inputBoxValue = parseInt(this.numberQuantity,10)
    },
},
}
</script>