<template>
  <div>
    <div v-if="info">
      <v-card outlined>
        <v-card-text>
          <v-row>
            <v-col cols="12" md="6">
              <v-img :src="info.image"></v-img>
            </v-col>
            <v-col>
              <h1> {{ info.title }} </h1>
              <div v-if="info.description">
                <h2 class="mt-4">{{ info.description.title }}</h2>
                <h3 class="mt-4">{{ info.description.sub_title }}</h3>
                <span v-for="(l, index) in info.description.li" :key="index">
                  <div>
                    <v-icon class="mr-2" color="success">mdi-check</v-icon> {{ l }}
                  </div>
                </span>
              </div>

              <v-row>
                <v-col>
                  <!-- <v-select
                    v-model="type"
                    variant="outlined"
                    :items="info.lists"
                    item-value="size"
                    item-title="size"
                    color="indigo"
                    density="compact"
                  >
                    <template #selection="{item: { raw }}">
                      ขนาด {{ raw.size }} - {{ raw.pricePerMeter }} / ม. - {{ raw.pricePerRoll }} / บ.
                    </template>
                     <template #item="{props, item: { raw }}">
                      <v-list-item v-bind="props">
                        {{ props }}
                        {{ raw.pricePerMeter }} / ม. - {{ raw.pricePerRoll }} / บ.
                      </v-list-item>
                    </template>
                  </v-select> -->
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      info: null
    }
  },
  methods: {
    async getData() {
      const res = await this.$axios.$get('./product.json')
      this.info = res.data.find(x => x.group_code == "greenhouse")
      this.info = this.info.products.find(x => x.product_code == this.$route.params.code)
    },
    goToPath(path) {
      this.$router.push(`products/detail/${path}`)
    }
  },
  created() {
    this.getData()
  },
}
</script>

<style lang="scss" scoped></style>