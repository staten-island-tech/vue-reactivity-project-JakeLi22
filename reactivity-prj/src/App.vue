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
    numberQuantity: '10000',
    types: [
      {
        cellId: 1, 
        seller: "Sanyo",
        cellModel: " NCR18650GA", 
        details: ["3450mAh","3.6V"],
        cellImage: "", 
        cellPrice: 6.75, 
        cellWeight: "48g",
        
      },
      {
          cellId: 2, 
          seller: "Panasonic",
        cellModel: "NCR18650BD", 
        details: ["3180mAh","3.6V"],
        cellImage: "", 
        cellPrice: 4.5, 
        cellWeight: "46.4g",
        
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