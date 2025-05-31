<template>
  <div class="page">
    <carouselImage />
    <productItem />
    <imageGallery />
  </div>
</template>

<script>
import carouselImage from "@/components/carousel-image.vue"
import productItem from "@/components/product-item.vue"
import imageGallery from "@/components/image-gallery.vue"
export default {
  components: { carouselImage, productItem, imageGallery },
}
</script>

<style lang="scss" scoped>

</style>