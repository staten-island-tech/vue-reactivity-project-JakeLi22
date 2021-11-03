<template>
  <div id="container">
    <h1 class="website-title">Battery Cells</h1>
    <div class="cell-options">
      <img :src="image"  alt="">
      <h1>{{cellType}} battery</h1>
      <h2>model: {{name}}</h2>
      <h2>seller: {{seller}}</h2>
      <h2>${{price}}</h2>
      <ul>
        <li v-for="property in properties" :key="property.propertyid">{{property}}</li>
      </ul>
    </div>
    <button class="red-button" v-on:click = 'clickRed'>red</button>
    <button class="gray-button" v-on:click = 'clickGray'>gray</button>

    <div class="quantity-div">
      <button v-on:click = 'decreaseQuantity'
      class="quantity-subtract-button">-</button>
      <input v-model='numberQuantity'
      class="quantityValue" type="number">
      <button v-on:click = 'increaseQuantity'
      class="quantity-add-button">+</button>
    </div>
    <button v-on:click = 'addToCart' class = "cart-button">Add to Cart</button>
    <h3>Cart:{{cartNumber}}</h3>

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
    cartNumber:0,
    index:0,
    image: require('./img/red_cell.jpg'),
    
    types: [
      {
        cellId: 1, 
        seller: "Sanyo",
        cellModel: " NCR18650GA", 
        details: ["3450mAh","3.6V", "48g"],
        cellPrice: 6.75, 
        
      },
      {
          cellId: 2, 
          seller: "Panasonic",
        cellModel: "NCR18650BD", 
        details: ["3180mAh","3.6V", "46.4g"],
        cellPrice: 4.5, 
        
      }
    ]
  }
},
computed:{
  name(){
  return this.types[this.index].cellModel; //create a variable so that when you select something the id changes
  },
  seller(){
    return this.types[this.index].seller;
  },
  price(){
    return this.types[this.index].cellPrice;
  },
  properties(){
    return this.types[this.index].details;
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
      const returnedNumber = parseInt(this.numberQuantity,10);
      const newCartNumber = returnedNumber + this.cartNumber;
      this.cartNumber = newCartNumber;
      console.log(newCartNumber);

    },  
    clickRed(){
      this.index = 0;
      if(this.index === 0){
         this.image= require('./img/red_cell.jpg');
      }
      else if(this.index === 1){
        this.image = require('./img/gray cell.jpg');
      }
    },
    clickGray(){
      this.index = 1;
      if(this.index === 0){
         this.image= require('./img/red_cell.jpg');
      }
      else if(this.index === 1){
        this.image = require('./img/gray cell.jpg');
      }

    },

},
}
</script>