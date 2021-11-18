<template>
  <div class="product-list">
    <div class="flex top-information">
       
      <h1>Iphone</h1>
      <my-input v-model="searchText" />
      {{ searchText }}
      <button>
        Найти
      </button>
    </div>
    
    <ul class="list-default flex">
      <li
        v-for="(product, index) in products"
        :key="index"
      >
        <product-card
          :title="product.title"
          :price="product.price"
          :img-url="product.imgUrl"
          :count="product.count"
          @addToBasket="addToBasket(index)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import ProductCard from './ProductCard'
import MyInput from './MyInput'



export default {
  name: 'ProductList',
  components: { ProductCard, MyInput },
  data() {
    return {
      searchText: '',
      products: [
        {
          title: 'Iphone 13',
          price: 80000,
          imgUrl: 'https://jjstore.ru/image/cache/catalog/iphone/iphone13/iphone-13-blue-2021-1181x865.png',
          count: 30
        },
        {
          title: 'Iphone 13 Pro',
          price: 99000,
          imgUrl: 'https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/iphone-13-pro-family-hero?wid=940&hei=1112&fmt=png-alpha&.v=1631220221000',
          count: 20
        },
        {
          title: 'Iphone 12',
          price: 60000,
          imgUrl: 'https://htstatic.imgsmail.ru/pic_image/c2aaf8b06c58a5f807248cd2704ebb62/450/450/1909768/',
          count: 23
        },
        {
          title: 'Iphone 11',
          price: 45000,
          imgUrl: 'https://pngimg.com/uploads/iphone_11/iphone_11_PNG38.png',
          count: 15
        },
        {
          title: 'Iphone XR',
          price: 40000,
          imgUrl: 'https://www.yablokitradein.ru/image/cache/catalog/xr%20all/jel-500x500.png',
          count: 17
        }
        
      ]
    }
  },
  methods: {
    addToBasket(index) {
      console.log(index)
    }
  }
}
</script>

<style >
.list-default {
  text-align: center;
}

</style>