<template>
  <div>
    <div v-if="info">
      <v-card min-height="90vh" bg-color="#eee" outlined>
        <v-card-text>
          <v-row>
            <v-col cols="12" md="4">
              <v-card outlined height="100%">
                <v-card-title>
                  <h1>{{ info.group_title_th }}</h1>
                </v-card-title>
                <v-card-text >
                  <div>
                    <div>
                      <h2>ฟิล์มคลุมโรงเรือนระดับพรีเมียม</h2>
                      <h3>ทนทาน ใช้งานคุ้ม เหมาะกับเกษตรยุคใหม่</h3>
                      <span>ฟิล์มคลุมโรงเรือนคุณภาพสูง ที่ออกแบบมาเพื่อช่วยให้พืชโตดี ให้ผลผลิตสูง และลดต้นทุน เหมาะกับทุกสภาพอากาศ ใช้งานง่าย อายุการใช้งานยาวนาน เป็นตัวช่วยสำคัญของเกษตรกรที่ต้องการเพิ่มประสิทธิภาพและทำเกษตรอย่างยั่งยืน</span>
                    </div>
                    <div class="mt-4">
                      <h2>จุดเด่นของฟิล์ม</h2>
                      <div>
                        <div class="d-flex">
                          <v-icon color="success">mdi-check-circle-outline</v-icon>
                          <h3 class="ml-2">แข็งแรงเป็นพิเศษ</h3>
                        </div>
                        <span>ทนลม ทนแรงฉีก ด้วยวัสดุพิเศษ ใช้ได้นาน คุ้มค่า</span>
                      </div>
                      <div>
                        <div class="d-flex">
                          <v-icon color="success">mdi-check-circle-outline</v-icon>
                          <h3 class="ml-2">แสงกระจายดี พืชโตสม่ำเสมอ</h3>
                        </div>
                        <span>ลดเงา จุดร้อน แสงเข้าทั่วถึง แม้ในส่วนล่างของพืช ช่วยให้โตเร็ว ให้ผลผลิตมาก</span>
                      </div>
                      <div>
                        <div class="d-flex">
                          <v-icon color="success">mdi-check-circle-outline</v-icon>
                          <h3 class="ml-2"> กันหยดน้ำ กันหมอก</h3>
                        </div>
                        <span>ลดหยดน้ำ ลดความชื้นสะสม ลดโรคพืช และเพิ่มแสงในโรงเรือน ใช้แล้วพืชโตไว เก็บเกี่ยวเร็ว</span>
                      </div>
                      <div>
                        <div class="d-flex">
                          <v-icon color="success">mdi-check-circle-outline</v-icon>
                          <h3 class="ml-2">ช่วยลดแมลงและโรค</h3>
                        </div>
                        <span>ฟิล์มป้องกันรังสี UV ลดแมลง เช่น เพลี้ย แมลงวันขาว และเชื้อราบางชนิด ลดการใช้สารเคมี</span>
                      </div>
                      <div>
                         <div class="d-flex">
                            <v-icon color="success">mdi-check-circle-outline</v-icon>
                            <h3 class="ml-2"> เก็บความร้อนได้ดีในเวลากลางคืน</h3>
                         </div>
                        <span>ช่วยรักษาอุณหภูมิ ลดปัญหาน้ำค้างแข็ง พืชไม่ชะงักโต เหมาะสำหรับพื้นที่หนาว</span>
                      </div>
                    </div>
                    <div>
                      <h3>มีหลายแบบให้เลือก</h3>
                      <h2>เลือกตามพืชที่ปลูกและสภาพอากาศ เช่น</h2>
                      <div class="d-flex">
                        <v-icon color="success">mdi-check-circle-outline</v-icon>
                        <h3 class="ml-2">แบบใส แสงตรงมาก</h3>
                      </div>
                      <div class="d-flex">
                        <v-icon color="success">mdi-check-circle-outline</v-icon>
                        <h3 class="ml-2">แบบกระจายแสงปานกลาง</h3>
                      </div>
                      <div class="d-flex">
                        <v-icon color="success">mdi-check-circle-outline</v-icon>
                        <h3 class="ml-2">แบบกระจายแสงสูง</h3>
                      </div>
                      <div>ทีมงานพร้อมให้คำแนะนำฟรี เพื่อเลือกฟิล์มที่เหมาะกับคุณที่สุด</div>
                    </div>
                    <div>
                      <h3>สนใจสอบถามเพิ่มเติม</h3>
                      <span>หากคุณมองหาฟิล์มโรงเรือนที่ทน คุ้มค่า และช่วยเพิ่มผลผลิต ทีมงานพร้อมให้คำแนะนำฟรี เพื่อเลือกฟิล์มที่เหมาะกับคุณที่สุด</span>
                      <h2>ติดต่อเราเลย! เราพร้อมให้คำปรึกษา</h2>
                    </div>
                  </div>
                </v-card-text>
              </v-card>
            </v-col>
            <v-col>
              <v-row>
                <v-col cols="12" sm="6" md="4" v-for="(item, index) in info.products" :key="index">
                  <v-card outlined :title="`${item.title}`" @click="goToPath(item.product_code)">
                    <v-card-text>
                      <v-img width="100%" :src="item.image"></v-img>
                    </v-card-text>
                  </v-card>
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
    async getData(){
      const res = await this.$axios.$get('./product.json')
      this.info = res.data.find(x => x.group_code == "greenhouse")
    },
    goToPath(path){
      this.$router.push(`/products/detail/${path}`)
    }
  },
  created() {
    this.getData()
  },
}
</script>

<style lang="scss" scoped>

</style>