<template>
  <v-app>
    <Header
      :clipped="clipped"
      :total-items="totalItems"
      @toggleRightDrawer="rightDrawer = !rightDrawer"
    />
    <v-main class="no-padding">
      <Nuxt />
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
      :overlay-opacity="0.1"
      width="460"
    >
      <Cart @close="rightDrawer = false" />
    </v-navigation-drawer>
    <Footer :fixed="fixed" />
  </v-app>
</template>

<script>
import { mapGetters } from 'vuex'
import Header from '~/components/common/Header.vue'
import Footer from '~/components/common/Footer.vue'
import Cart from '~/components/Cart.vue'
export default {
  name: 'DefaultLayout',
  components: {
    Header,
    Footer,
    Cart
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Voxel Store'
    }
  },
  computed: {
    ...mapGetters('cart', ['totalItems']),
    cart () {
      return this.$store.state.cart
    }
  }
}
</script>

<style lang="scss">
/* Global or shared styles */
.no-shadow {
  box-shadow: none !important;
}

.no-padding {
  padding: 0;
  margin: 0;
}

.ellipsis {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
</style>
