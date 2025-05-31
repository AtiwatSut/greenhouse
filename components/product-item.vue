<template>
  <div class="product py-10 px-4">
    <div class="text-h4 font-weight-bold text-center mb-6">สินค้า</div>
    <v-row justify="center" align="center" dense>
      <v-col v-for="(group, index) in groups" :key="index" cols="6" sm="4" md="3">
        <v-card outlined class="text-center hover-card" @click="goToPath(group.group_code)">
            <v-card-text>
              <v-img :src="group.image" height="100%" contain></v-img>
              <h2 class="mt-3 font-weight-bold">{{ group.group_title_th }}</h2>
            </v-card-text>
          </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        groups: [
          {
            "group_id": 1,
            "group_code": "greenhouse",
            "group_title": "Greenhouse Film",
            "group_title_th": "พลาสติกคลุมโรงเรือน",
            "image": require("~/assets/images/slide/film-1.png")
          },
          {
            "group_id": 2,
            "group_code": "insect_mesh",
            "group_title": "Insect Mesh",
            "group_title_th": "ตาข่ายกันแมลง",
            "description": "ฟิล์มคลุมโรงเรือนระดับพรีเมียมได้รับความเชื่อถือจากเกษตรกร ั ท่วโลก ั ด้วยความทนทานที่เหนือ กว่ามาตรฐานการออกแบบ อายุการใช้งานขึ้นอยู่กับคุณภาพของวัสดุ เทคนิคการผลิต และสภาพ แวดล้อมที่ใช้งาน",
            "image": require("~/assets/images/slide/Film-150.png")
          }
        ]
      }
    },
    methods: {
      goToPath(path){
        this.$router.push(`/products/${path}`)
      }
    },
  }
</script>

<style lang="scss" scoped>
.product {
  background-color: #FFF;
  .hover-card {
    cursor: pointer;
    transition: transform 0.2s;
    
    &:hover {
      transform: translateY(-20px);
    }
  }
}
</style>