<template>
  <div>
    <v-carousel class="slide-image" cycle hide-delimiter-background height="800">
      <v-carousel-item v-for="(item, index) in lists" :key="index" cover :src="item.image">
        <div class="title text-center pt-10 white--text">
          <h1>โรงเรือนเพาะปลูก</h1>
          <div class="font-weight-bold">สร้างสภาพแวดล้อมที่เหมาะสม <br> เพื่อการเพาะปลูกที่มีคุณภาพและยั่งยืน</div>
        </div>
        <div class="description" outlined>
          <v-card class="pa-5" outlined>
            <v-card-text>
              <div class="detail text pl-4 white--text">
                <h2 class="">{{ item.title }}</h2>
                <div v-html="item.text"></div>
                <div class="mt-4 text-right">
                  <v-btn class="white--text rounded-pill" color="orange" elevation="0">
                    อ่านเพิ่มเติม
                  </v-btn>
                </div>
              </div>
            </v-card-text>
          </v-card>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: [
        {
          text: `เลือกพลาสติกที่มีความทนทาน กรองแสงได้ดี และเหมาะกับสภาพอากาศ<br>อายุการใช้งานยาวนาน ช่วยลดต้นทุนระยะยาว`,
          image: require("~/assets/images/gallery/image-1.jpg"),
          title: 'วิธีเลือกเนื้อพลาสติก'
        },
        {
          text: `ควบคุมอุณหภูมิ ความชื้น ป้องกันแมลง และเพิ่มผลผลิต<br>เหมาะสำหรับการเพาะปลูกเชิงพาณิชย์และงานวิจัย`,
          image: require("~/assets/images/gallery/image-2.jpg"),
          title: 'ทำไมต้องใช้ Greenhouse'
        },
        {
          text: `ควบคุมอุณหภูมิ ความชื้น ป้องกันแมลง และเพิ่มผลผลิต<br>เหมาะสำหรับการเพาะปลูกเชิงพาณิชย์และงานวิจัย`,
          image: require("~/assets/images/gallery/image-3.jpg"),
          title: 'ทำไมต้องใช้ Greenhouse'
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
::v-deep .slide-image {
  position: relative !important;

  .title {
    h1 { font-size: 70px; line-height: 1; }
    div { font-size: 20px; }
  }
  .description {
    position: absolute;
    top: 50%;
    left: 50px;
    
    .v-card {
      background-color: #ffffff5a !important;
    }
    .detail {
      
    }

    h2 { font-size: 40px; }
  }
}
</style>