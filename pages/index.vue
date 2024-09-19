<template>
  <v-row justify="center" align="center" role="main">
    <Hero />
    <Filter />
    <Products :products="products" />
  </v-row>
</template>

<script>
import Hero from '~/components/Hero.vue'
import Filter from '~/components/Filter.vue'
import Products from '~/components/Products.vue'
export default {
  name: 'IndexPage',
  components: {
    Hero,
    Filter,
    Products
  },
  asyncData ({ app }) {
    return app.$axios.$get('https://fakestoreapi.com/products')
      .then(data => ({ products: data }))
      .catch((error) => {
        window.console.error('Error fetching product data:', error)
        return { products: [] }
      })
  },
  data () {
    return {
      products: []
    }
  },
  head () {
    const title = 'Voxel Store'
    const description = 'Voxel Store - A basic eCommerce store'

    return {
      title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: description
        }
      ]
    }
  }
}
</script>
