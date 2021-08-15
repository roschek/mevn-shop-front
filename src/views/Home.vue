<template>
  <div class="home">   
    <ul class="product_list">
      <product-card 
      v-for="product in products"
      :key="product.id"
      :title="product.title"
      :price="product.price"
      :imageUrl="product.imageUrl"/>
    </ul>
  </div>
</template>

<script>
import { mapGetters, mapActions} from 'vuex'

export default {
  name: 'Home',
  components: {
   ProductCard: () => import('@/components/ProductCard')
  },

  mounted() {
    this.fetchProducts();
  },

  computed:{
    ...mapGetters({
      products: 'products'
    })
  },
  methods:{
    ...mapActions({
      fetchProducts:'fetchProducts'
    })
  }
}
</script>

<style scoped>
  .product_list{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 1240px;
    margin: 50px auto;
    gap:40px;
    padding: 0;
  }
</style>
