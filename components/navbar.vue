<template>
  <div class="navbar">
    <v-app-bar elevation="0">
      <v-app-bar-nav-icon class="d-block d-md-none" @click="active = true"></v-app-bar-nav-icon>
      <v-toolbar-title @click="goToPath('/')"> Green House </v-toolbar-title>
      <v-spacer></v-spacer>
      <div v-for="(item, index) in menus" :key="index" class="d-none d-md-flex align-center">
         <v-btn v-if="item.type === 'menu'" @click="goToPath(item.path)" class="mr-10" text>{{ item.title }}</v-btn>

         <v-menu v-else-if="item.type === 'group'" open-on-hover offset-y>
            <template #activator="{ on, attrs }">
              <v-btn text v-bind="attrs" v-on="on" class="mr-10">{{ item.title }} <v-icon right size="18">{{ item.icon }}</v-icon></v-btn>
            </template>

            <v-list dense class="main-menu-dropdown">
              <v-menu v-for="(list, i) in item.lists" :key="i" open-on-hover offset-x location="end">
                <template #activator="{ on, attrs }">
                  <v-list-item v-bind="attrs" v-on="on" class="submenu-activator">
                    <v-list-item-title @click="goToPath(list.path)" >{{ list.title }}</v-list-item-title>
                    <template v-slot:append-icon>
                      <v-icon size="18">{{ list.icon }}t</v-icon>
                    </template>
                  </v-list-item>
                </template>
              </v-menu>
            </v-list>
         </v-menu>
      </div>
    </v-app-bar>

    <v-navigation-drawer v-model="active" absolute temporary style="width: 300px;">
      <v-list class="main-menu-dropdown">
        <v-list-item v-if="item.type == 'menu'" v-for="(item, index) in menus" :key="index" @click="goToPath(item.path)">
          <v-list-item-icon  @click="goToPath(item.path)">
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-title>{{item.title}}</v-list-item-title>
        </v-list-item>
        <v-list-group no-action sub-group v-if="item.type == 'group'" v-for="(item, index) in menus" :key="index">
          <template v-slot:activator>
            <v-list-item>
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-title>{{item.title}}</v-list-item-title>
            </v-list-item>
          </template>

          <v-list-item v-for="(list, i) in item.lists" :key="i" link @click="goToPath(list.path)">
            <v-list-item-icon>
              <v-icon>{{ list.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title v-text="list.title"></v-list-item-title>
          </v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false,
      menus: [
        { title: "หน้าแรก", icon: "mdi-home-outline", path: "/", lists: [], type: "menu" },
        {
          title: "สินค้า",
          icon: "mdi-store-outline",
          path: "/products",
          lists: [
            { title: "พลาสติกคลุมโรงเรือน", icon: "mdi-store-outline", path: "/products/greenhouse" },
            { title: "มุ้งโรงเรือน", icon: "mdi-store-outline", path: "/products/insect-mesh" },
            // { title: "รางและสปริงโรงเรือน", icon: "mdi-store-outline", path: "/spring-rails" },
          ],
          type: "group"
        },
        {
          title: "คู่มือ",
          icon: "mdi-book-open-page-variant-outline",
          path: "/how-to-pay",
          lists: [
            { title: "วิธีสั่งซื้อสินค้า", icon: "mdi-book-open-page-variant-outline", path: "/how-to-pay" },
            { title: "วิธีการจัดส่ง", icon: "mdi-book-open-page-variant-outline", path: "/shipping" },
            { title: "ช่องทางการชำระเงิน", icon: "mdi-book-open-page-variant-outline", path: "/payment" },
          ],
          type: "group"
        },
        { title: "บทความ", icon: "mdi-post-outline", path: "/article", lists: [], type: "menu" },
        { title: "เกี่ยวกับเรา", icon: "mdi-information-outline", path: "/about", lists: [], type: "menu" },
        { title: "ติดต่อเรา", icon: "mdi-card-account-phone-outline", path: "/contacts", lists: [], type: "menu" },
      ]
    }
  },
  methods: {
    goToPath(path){
      this.$router.push(path)
    }
  },
}
</script>

<style lang="scss" scoped>
::v-deep .navbar {
  position: sticky !important;
  position: -webkit-sticky !important; 
  top: 0 !important;
}
</style>