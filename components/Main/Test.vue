<template>
  <div class="py-12 test">
    <v-container>
      <div class="text-center pb-16">
        <h2 class="text-h4">
          Testimonial
        </h2>
        <h4 class="text-h5">
          What is says our customer
        </h4>
      </div>

      <v-carousel
        cycle
        hide-delimiter-background
        :show-arrows="$vuetify.breakpoint.mdAndUp ? true : false"
        height="auto"
      >
        <template v-slot:prev="{ on, attrs }">
          <v-hover v-slot="{ hover }">
            <v-btn
              v-bind="attrs"
              v-on="on"
              fab
              icon
            >
              <img :src="hover ? 'img/prev.png' : 'img/prev-black.png'" alt="">
            </v-btn>
          </v-hover>
        </template>
        <template v-slot:next="{ on, attrs }">
          <v-hover v-slot="{ hover }">
            <v-btn
              v-bind="attrs"
              v-on="on"
              fab
              icon
            >
              <img :src="hover ? 'img/next.png' : 'img/next-black.png'" alt="">
            </v-btn>
          </v-hover>
        </template>
        <v-carousel-item
          v-for="(slide, i) in slides"
          :key="i"
        >
          <v-card outlined tile class="test-card mx-auto">
            <v-card-text class="pa-2">
              <v-row
                class="ma-0"
                align="center"
                justify="center"
              >
                <v-col md="5" cols="12">
                  <div class="client d-flex align-center">
                    <div class="client-img mr-6">
                      <img src="img/client.png" alt="" width="100%">
                    </div>
                    <div class="client-info">
                      <h4 class="text-h6 font-weight-black black--text">
                        Aliqua
                      </h4>
                      <h5 class="subtitle-1 font-weight-bold client-desc">
                        Consectetur adipiscing
                      </h5>
                    </div>
                  </div>
                </v-col>
                <v-col md="7" cols="12">
                  <p class="subtitle-1 font-weight-bold ma-0">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrudLorem ipsum
                  </p>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-carousel-item>
      </v-carousel>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slides: [
        {},
        {},
        {}
      ]
    }
  }
}
</script>

<style>
.v-window__prev, .v-window__next {
  background: transparent !important;
}
</style>
<style lang="scss" scoped>
.test {
  .test-card {
    display: flex;
    align-items: center;
    width: 85%;
    border-color: #fbb534;
    .client {
      .client-img {
        img {
          vertical-align: middle;
        }
      }

      .client-desc {
        color: #f6d768;
      }
    }
  }
}
</style>
