<template>
  <div id="container">
    <h1 class="website-title">Battery Cells</h1>
    <div class="cell-options">
      <img v-bind:src="{{img}}" alt="">
      <h1>{{cellType}}</h1>
      <h2>{{name}}</h2>
      <h2>{{seller}}</h2>
      <h2>{{price}}</h2>
      <ul>
        <li>details</li>
      </ul>

      <!-- 
        img
        list
        cell name  
        quantity 2 button with plus and minus
          v-on:click="name of the function"
        price
       -->
    </div>

    <div class="quantity-div">
      <button v-on:click = 'decreaseQuantity'
      class="quantity-subtract-button">-</button>
      <input v-model='numberQuantity'
      class="quantityValue" type="number">
      <button v-on:click = 'increaseQuantity'
      class="quantity-add-button">+</button>
    </div>
    <button v-on:click = 'addToCart' class = "cart-button">Add to Cart</button>
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
    //returnedNumber: parseInt(this.numberQuantity,10), //set this is a global variable in data --> not working yet
    cellType: "lithium-ion", 
    numberQuantity: '',
    types: [
      {
        cellId: 1, 
        seller: "Sanyo",
        cellModel: " NCR18650GA", 
        details: ["3450mAh","3.6V", "48g"],
        cellImage: "@/assests/img/red_cell.jpg", 
        cellPrice: 6.75, 
        
      },
      {
          cellId: 2, 
          seller: "Panasonic",
        cellModel: "NCR18650BD", 
        details: ["3180mAh","3.6V", "46.4g"],
        cellImage: "@/assests/img/gray cell.jpg", 
        cellPrice: 4.5, 
        
      }
    ]
  }
},
computed:{
  name(){
  return this.types[0].cellModel; //create a variable so that when you select something the id changes
  },
  seller(){
    return this.types[0].seller;
  },
  price(){
    return this.types[0].cellPrice;
  },
  img(){
    return this.types[0].cellImage;
  },

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