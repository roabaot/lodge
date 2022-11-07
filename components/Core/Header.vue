<template>
  <div>
    <v-app-bar
      dark
      color="transparent"
      class="app-bar"
      flat
    >
      <v-container class="d-flex" fluid>
        <!-- Logo -->
        <v-toolbar-title>
          <div
            style="cursor: pointer;"
            class="d-flex align-end black--text font-weight-black headline mt-2"
            @click="$nuxt.$router.push('/')"
          >
            <img src="https://i.postimg.cc/8zg7bHJx/logo.png" alt="" width="30" class="mx-1">
            <span>LODGE</span>
          </div>
        </v-toolbar-title>

        <v-spacer />

        <v-spacer />

        <!-- navigation -->
        <div v-if="!$vuetify.breakpoint.smAndDown">
          <v-btn text class="mx-1 subtitle-1 text-capitalize font-weight-light" @click="scroll('home')">
            Home
          </v-btn>
          <v-btn text class="mx-1 subtitle-1 text-capitalize font-weight-light" @click="scroll('about')">
            About
          </v-btn>
          <v-btn text class="mx-1 subtitle-1 text-capitalize font-weight-light" @click="scroll('jewellery')">
            Jewellery
          </v-btn>
          <v-btn text class="mx-1 subtitle-1 text-capitalize font-weight-light" @click="scroll('contact')">
            Contact Us
          </v-btn>
          <v-btn text class="mx-1 subtitle-1 text-capitalize font-weight-light">
            Login
          </v-btn>

          <span class="cart">
            <v-btn icon>
              <img src="https://i.postimg.cc/ZRrLx83X/cart.png" alt="" width="25" height="23">
              <span class="cart-number">
                0
              </span>
            </v-btn>
          </span>
          <v-btn icon>
            <img src="https://i.postimg.cc/VkNyd6Mj/search-icon.png" alt="" width="23">
          </v-btn>
        </div>

        <!-- breakpoint -->
        <!-- #menu -->
        <div v-else>
          <span class="cart">
            <v-btn icon>
              <img src="https://i.postimg.cc/ZRrLx83X/cart.png" alt="" width="25" height="23">
              <span class="cart-number">
                0
              </span>
            </v-btn>
          </span>
          <v-btn icon>
            <img src="https://i.postimg.cc/VkNyd6Mj/search-icon.png" alt="" width="23">
          </v-btn>
          <v-menu
            transition="slide-y-transition"
            offset-y
            bottom
            max-width="100%"
            nudge-width="100%"
            min-width="100%"
            style="z-index: 13"
          >
            <template #activator="{ on, attrs }">
              <v-app-bar-nav-icon
                v-bind="attrs"
                v-on="on"
              />
            </template>
            <v-list class="mt-2" color="#fbc54c">
              <v-list-item
                v-for="(item, i) in items"
                :key="i"
                class="text-center"
                @click="scroll(item.to)"
              >
                <v-list-item-title class="white--text">{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>
      </v-container>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  props: {
    drawer: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {
      Drawer: this.drawer,
      items: [
        { title: 'Home', to: 'home' },
        { title: 'About', to: 'about' },
        { title: 'Jewellery', to: 'jewellery' },
        { title: 'Contact Us', to: 'contact-us' },
        { title: 'Login', to: 'login' }
      ]
    }
  },
  methods: {
    onDrawer () {
      this.Drawer = !this.Drawer
      this.$emit('drawer', true)
    },
    scroll (refName) {
      const element = document.getElementById(refName)
      element.scrollIntoView({ behavior: 'smooth' })
    }
  }
}
</script>

<style lang="scss" scoped>
.app-bar {
  .v-toolbar__content {
    padding: 0 !important;

    .cart {
      position: relative;

      .cart-number {
        position: absolute;
        top: 3px;
        left: 2px;
        right: 0;
      }
    }
  }
}
</style>
