<template>
  <div>
<CheeseCard v-for="destination in destinations" 
:key="destination.name" 
:Destination="destination"/>
  </div>
</template>

<script setup>
 import CheeseCard from "@/components/icons/CheeseCard.vue"
 const destinations = [
        {
          name: "Cottage",
          price: 1300,
          img: "https://cheesemaking.com/cdn/shop/products/cottage-cheese-1_grande.jpg?v=1529434175",
        },
        {
          name: "Cream",
          price: 800,
          img: "https://upload.wikimedia.org/wikipedia/commons/f/f7/Philly_cream_cheese.jpg",
        },
        {
          name: "Mozzarella",
          price: 1200,
          img: "https://www.seriouseats.com/thmb/0LrG8tB4BkzQarr2fqrpykcaDBg=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/__opt__aboutcom__coeus__resources__content_migration__serious_eats__seriouseats.com__recipes__images__2015__10__20151017-pies-vicky-wasik-2-6f491edb6065485a86d6af639a592298.jpg",
        },
        {
          name: "Bel paese",
          price: 900,
          img: "https://m.media-amazon.com/images/I/41kT2d78y5L.jpg",
        },
        {
          name: "Brie",
          price: 400,
          img: "https://cdn.apartmenttherapy.info/image/upload/f_auto,q_auto:eco,c_fill,g_center,w_730,h_913/k%2FPhoto%2FSeries%2F2023-11-how-to-eat-brie%2Fhow-to-eat-brie-381",
        },
        {
          name: "Camembert",
          price: 800,
          img: "https://marinfrenchcheese.com/wp-content/uploads/2021/10/Product-Page_Petite-Camembert_Beauty-Shot.jpg",
        },
        {
          name: "Cheddar",
          price: 800,
          img: "https://shop.burnettdairy.com/cdn/shop/products/BD_MildChed.jpg?v=1589903792",
        },
        {
          name: "Cheshire",
          price: 800,
          img: "https://www.gourmetdash.com/media/catalog/product/cache/8794a98778c2ca77788a2eb8b07fbd40/1/0/1050_beauty_so9nea2ke2blirmu_1.jpg",
        },
        {
          name: "Derby",
          price: 800,
          img: "https://s3.us-east-2.amazonaws.com/cheesemaking-supply-co/014bd94fee1e456d98c98a158d90b6dc.jpg",
        },
        {
          name: "Parmesan",
          price: 800,
          img: "https://frankenmuthcheesehaus.com/cdn/shop/products/PXL_20210430_200530224.PORTRAIT_1019x700.jpg?v=1619980804",
        },
        {
          name: "Pecorino Romano",
          price: 800,
          img: "https://www.cheese.com/media/img/cheese/Pecorino_romano_cheese.jpg",
        },
        {
          name: "Caciocavallo",
          price: 800,
          img: "https://www.cheese.com/media/img/cheese/Caciocavallo.jpg",
        },
        {
          name: "Danish Blue",
          price: 800,
          img: "https://dorothy-lane-market.s3.us-east-2.amazonaws.com/shop/items/danish-blue-1_662x450.JPEG",
        },
        {
          name: "Dorset Blue",
          price: 800,
          img: "https://upload.wikimedia.org/wikipedia/commons/6/67/Dorset_Blue_Vinney_cheese.jpg",
        },
        {
          name: "Gorgonzola",
          price: 800,
          img: "https://www.cheese.com/media/uploads/blog/2023/05/gorgonzola.jpg",
        },
      ]
</script>

<style scoped>

</style>
