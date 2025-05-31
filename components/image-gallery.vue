<template>
  <div class="bg-white">
    <v-container>
      <div class="d-flex justify-center my-8">
        <h1> ตัวอย่างโรงเรือนที่ประกอบ </h1>
      </div>
      <v-row class="px-4">
        <v-col v-for="(item, n) in items" :key="n" class="d-flex child-flex" cols="12" sm="6" md="4">
          <v-img :lazy-src="item.image" :src="item.image" aspect-ratio="1" class="bg-grey-lighten-2 reduced-image" cover
            @click="showImg(n)" />
        </v-col>
      </v-row>
      <div class="d-flex justify-center my-8">
        <b>
          <v-btn size="x-large" block color="success" @click="goToLink('YOUR_DESIRED_LINK_HERE')">
            กดตรงนี้เพื่อดูเพิ่มเติม
          </v-btn>
        </b>
      </div>

    </v-container>

    <vue-easy-lightbox
      escDisabled
      moveDisabled
      :visible="show"
      :imgs="images"
      :index="indexRef"
      @hide="show = false"
    ></vue-easy-lightbox>
  </div>
</template>

<script>
import VueEasyLightbox from 'vue-easy-lightbox'
export default {
  components: { VueEasyLightbox },
  data() {
    return {
      indexRef: null,
      show: false,
      items: [
        { image: require("~/assets/images/gallery/image-1.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-2.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-3.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-4.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-5.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-6.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-7.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-8.jpg"), router: "" },
        { image: require("~/assets/images/gallery/image-9.jpg"), router: "" },
      ]
    }
  },
  computed: {
    images(){
      return this.items.map(x => x.image)
    }
  },
  methods: {
    showImg(index){
      console.log('index: ', index);
      this.indexRef = index
      this.show = true
    }
  },
}
</script>

<style lang="scss" scoped>
.reduced-image {
  cursor: pointer;
  transition: 0.3s;

  &:hover {
    transform: scale(1.1);
  }
}
</style>