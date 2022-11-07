<template>
  <div class="py-12">
    <section class="special d-flex align-end">
      <div class="special-box">
        <img src="https://i.postimg.cc/8ctQZN4L/design-1.png" alt="" width="100%">
      </div>

      <v-container>
        <v-card class="special-card">
          <v-row
            class="ma-0 flex-wrap-reverse"
            align="center"
            justify="center"
          >
            <v-col md="5" cols="12" class="text-center">
              <h5 class="text-h5 special-text">
                SPECIAL
              </h5>
              <h4 class="text-h4 mb-6">
                Wedding Ring
              </h4>
              <v-btn outlined tile class="subtitle-1 text-capitalize font-weight-bold">Buy Now</v-btn>
            </v-col>
            <v-col md="7" cols="12">
              <div class="special-img">
                <img src="https://i.postimg.cc/cHq15MRc/ring-img.jpg" alt="" width="100%">
              </div>
            </v-col>
          </v-row>
        </v-card>
      </v-container>
    </section>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.special {
  position: relative;

  .special-box {
    position: absolute;
    bottom: 0;
    left: 0;
    -webkit-transform: translateY(-50%);
    transform: translateY(-50%);
    width: 75px;
  }

  .special-card {
    box-shadow: 0px 0px 56px 1px rgb(0 0 0 / 8%) !important;
    .special-text {
      color: #fbb534;
    }
    .special-img {
      img {
        vertical-align: middle;
      }
    }
  }
}
</style>
