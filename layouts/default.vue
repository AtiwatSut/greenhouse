<template>
  <v-app>
    <navbar />
    <nuxt />
    <custom-footer />
  </v-app>
</template>

<script>
import navbar from '@/components/navbar.vue'
import customFooter from '@/components/custom-footer.vue'

export default {
  components: { navbar, customFooter },
  data () {
    return {   
    }
  } ,
}
</script>
<style lang="scss">
  v-app , .v-application { 
    min-height:100%;

    .container {
      max-width: 840px !important;
    }
  }
</style>