<template>
  <v-row justify="center" align="center" role="main">
    <vox-hero role="banner" />
    <vox-filter role="search" />
    <vox-products :products="products" role="region" aria-label="Products" />
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
  head () {
    const title = 'Voxel Store'
    const description = 'Voxel Store - A Basic e-Commerce Website'

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
