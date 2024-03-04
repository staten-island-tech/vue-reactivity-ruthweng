<template>
  <div id="app">
  <section id="userInput">
    <h1 id="header">A Very Cheesy Store!</h1>
    <div class="cheese-types">
    <Card
      class="type"
      v-for="(cheeseType, index) in cheeseTypes"
      @addCheese="addCheese(index)"
      :key="index"
      :cheese="cheeseType.cheese"
      :img="cheeseType.img"
      :price="cheeseType.price"
    />
  </div>
  </section>

  <section id="shoppingCart">
    <h1>Your Cart</h1>
    <Cart
      class="cart"
      v-for="(cheeseType, index) in order"
      :key="index"
      :order="cheeseType.cheese"
      :price="cheeseType.price"
    />
    <h2 class = subtotal>Subtotal: ${{ subtotal }}</h2>
    <button class="buttons" @click="remove()">Remove Last Chez</button>
    <button class="buttons" @click="removeAllCheese()">Remove All Cheeses</button>
    </section>
  </div>
</template>

<script>
import Card from "./components/CheeseCard.vue";
import Cart from "./components/CheeseCart.vue";
export default {
  cheese: "App",
  components: {
    Card,
    Cart,
  },
  data() {
  return {
    subtotal: 0,
    selectedCheese: 0,
    cheeseTypes: [
       {
         cheese: "Cottage",
         price: 1300,
         img: "https://cheesemaking.com/cdn/shop/products/cottage-cheese-1_grande.jpg?v=1529434175",
       },
       {
         cheese: "Cream",
         price: 800,
         img: "https://upload.wikimedia.org/wikipedia/commons/f/f7/Philly_cream_cheese.jpg",
       },
       {
         cheese: "Mozzarella",
         price: 1200,
         img: "https://www.seriouseats.com/thmb/0LrG8tB4BkzQarr2fqrpykcaDBg=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/__opt__aboutcom__coeus__resources__content_migration__serious_eats__seriouseats.com__recipes__images__2015__10__20151017-pies-vicky-wasik-2-6f491edb6065485a86d6af639a592298.jpg",
       },
       {
         cheese: "Bel paese",
         price: 900,
         img: "https://m.media-amazon.com/images/I/41kT2d78y5L.jpg",
       },
       {
         cheese: "Brie",
         price: 400,
         img: "https://cdn.apartmenttherapy.info/image/upload/f_auto,q_auto:eco,c_fill,g_center,w_730,h_913/k%2FPhoto%2FSeries%2F2023-11-how-to-eat-brie%2Fhow-to-eat-brie-381",
       },
       {
         cheese: "Camembert",
         price: 800,
         img: "https://marinfrenchcheese.com/wp-content/uploads/2021/10/Product-Page_Petite-Camembert_Beauty-Shot.jpg",
       },
       {
         cheese: "Cheddar",
         price: 800,
         img: "https://shop.burnettdairy.com/cdn/shop/products/BD_MildChed.jpg?v=1589903792",
       },
       {
         cheese: "Cheshire",
         price: 800,
         img: "https://www.gourmetdash.com/media/catalog/product/cache/8794a98778c2ca77788a2eb8b07fbd40/1/0/1050_beauty_so9nea2ke2blirmu_1.jpg",
       },
       {
         cheese: "Derby",
         price: 800,
         img: "https://s3.us-east-2.amazonaws.com/cheesemaking-supply-co/014bd94fee1e456d98c98a158d90b6dc.jpg",
       },
       {
         cheese: "Parmesan",
         price: 800,
         img: "https://frankenmuthcheesehaus.com/cdn/shop/products/PXL_20210430_200530224.PORTRAIT_1019x700.jpg?v=1619980804",
       },
       {
         cheese: "Pecorino Romano",
         price: 800,
         img: "https://www.cheese.com/media/img/cheese/Pecorino_romano_cheese.jpg",
       },
       {
         cheese: "Caciocavallo",
         price: 800,
         img: "https://www.cheese.com/media/img/cheese/Caciocavallo.jpg",
       },
       {
         cheese: "Danish Blue",
         price: 800,
         img: "https://dorothy-lane-market.s3.us-east-2.amazonaws.com/shop/items/danish-blue-1_662x450.JPEG",
       },
       {
         cheese: "Dorset Blue",
         price: 800,
         img: "https://upload.wikimedia.org/wikipedia/commons/6/67/Dorset_Blue_Vinney_cheese.jpg",
       },
       {
         cheese: "Gorgonzola",
         price: 800,
         img: "https://www.cheese.com/media/uploads/blog/2023/05/gorgonzola.jpg",
       },
     ]
,
    order: [],
    orderPrice: [],
  };
  },
methods: {
  addCheese(index) {
    this.order.push(this.cheeseTypes[index]);
    this.orderPrice.push(this.cheeseTypes[index].price);
    this.subtotal = this.subtotal + this.cheeseTypes[index].price;
},
  remove() {
  if (this.order.length !== 0) {
    this.subtotal =
    this.subtotal - this.orderPrice[this.orderPrice.length - 1];
    this.order.pop();
    this.orderPrice.pop();
  }
},
  removeAllCheese() {
    this.order = [];
    this.orderPrice = [];
    this.subtotal = 0;
  },
},
};
</script>

<style lang="css">
#header {
  margin-top: 2.3rem;
  text-align: center;
  color: #000000;
  font-family: 'Times New Roman', Times, serif;
  font-size: 5rem;
  margin-bottom: 0.7rem;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  display: flex;
  flex-direction: column;
  background-color: hsl(50, 52%, 85%);
  color: #000000;
  margin-bottom: 2rem;
}
.img {
  height: 5%;
  width: auto;
  
}

.subtotal {
  font-size: 1.9rem;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
#shoppingCart {
  background-color: #e4663c;
  border: 10px hsl(27, 56%, 52%) solid;
  border-radius: 10px;
  margin-top: 5rem;
  margin-bottom: 3.7rem;
  height: auto;
  color: #000000;
  width: 80vw;
  margin-left: 6rem;
  font-size: 1.5rem;
  flex-direction: column;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
.cheese-types {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  flex-direction: row;
}

.buttons {
  margin-bottom: 1rem;
  font-size: 1.3rem;
  justify-content: center;
  border-radius: 10px;
  width: 20%;
}
section {
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>./components/CheeseCard.vue./components/CheeseCart.vue
