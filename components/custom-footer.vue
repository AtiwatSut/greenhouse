<template>
  <div class="footer">
    <v-row class="content pa-4">
      <v-col cols="12" md="auto" class="text-center" >
        <iframe
          width="500"
          height="300"
          style="border:0"
          loading="lazy"
          allowfullscreen
          referrerpolicy="no-referrer-when-downgrade"
          src="https://www.google.com/maps?q=13.784631008382554, 100.5789684171748&hl=th&z=14&output=embed">
        </iframe>
      </v-col>
      <v-col>
        <v-row>
          <v-col v-for="(section, i) in sections" :key="i" cols="12" md="3" class="text-center" >
            <h3 class="mb-4">{{ section.title }}</h3>
            <div class="py-1" v-for="(item, j) in section.items" :key="j">
              <div @click="item.link && goToLink(item.link)" >
                {{ item.label }}
              </div>
            </div>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        sections: [
          {
            title: 'ติดต่อเรา',
            items: [
              { label: 'เบอร์โทร : 062-999-9999', link: null },
              { label: 'อีเมล : admin@gmail.com', link: null },
            ],
          },
          {
            title: 'หมวดหมู่สินค้า',
            items: [
              { label: 'พลาสติกคลุมโรงเรือน', link: '/plastic-greenhouse' },
              { label: 'มุ้งโรงเรือน', link: '/net' },
              { label: 'รางและสปริงโรงเรือน', link: '/spring-rails' },
            ],
          },
          {
            title: 'ช่วยเหลือ',
            items: [
              { label: 'การสั่งซื้อ', link: '/help-1' },
              { label: 'การชำระเงิน', link: '/help-2' },
              { label: 'นโยบายคืนเงิน', link: '/help-3' },
            ],
          },
          {
            title: 'เกี่ยวกับเรา',
            items: [
              { label: 'ประวัติ', link: '/about' },
              { label: 'ทีมงาน', link: '/about-us-2' },
              { label: 'ติดต่อเรา', link: '/contacts' },
            ],
          },
        ]
      }
    },
  }
</script>

<style lang="scss" scoped>
.footer {
  position: relative;
  width: 100%;
  overflow: hidden;

   &::before {
    content: "";
    position: absolute;
    top: 0; left: 0;
    width: 100%;
    height: 100%;
    background: url('~/static/slide/slide-3.png')  no-repeat center center / cover;
    opacity: 0.2;
    z-index: 1;
  }

  .content {
    position: relative;
    z-index: 2;
  }
  
}
</style>