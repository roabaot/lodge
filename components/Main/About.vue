<template>
  <div class="py-12">
    <section class="about d-flex align-end">
      <div class="about-box">
        <img src="https://i.postimg.cc/mDy0rB0K/design-2.png" alt="" width="100%">
      </div>

      <v-container>
        <v-row
          class="ma-0 flex-wrap-reverse"
          align="center"
          justify="center"
        >
          <v-col md="6" cols="12">
            <h2 class="text-h4 my-4">
              About Jewellery Shop
            </h2>
            <p class="subtitle-1 mb-16 pt-6">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrudLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
            </p>
            <v-btn tile color="black" class="subtitle-1 px-11 text-capitalize white--text" :class="$vuetify.breakpoint.mdAndUp ? 'py-6' : ''">
              Read More
            </v-btn>
          </v-col>
          <v-col md="6" cols="12">
            <div class="about-img">
              <img src="https://i.postimg.cc/RFzZ8159/about-img.png" alt="" width="100%">
            </div>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.about {
  position: relative;
  .about-box {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 75px;
  }
}
</style>
