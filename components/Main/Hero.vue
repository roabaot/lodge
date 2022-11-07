<template>
  <div>
    <v-img
      src="https://i.postimg.cc/0jPn2JYt/hero-bg.png"
      lazy-src="https://i.postimg.cc/0jPn2JYt/hero-bg.png"
      :position="$vuetify.breakpoint.mdAndUp ? 'bottom right' : 'top'"
      class="hero"
      :class="$vuetify.breakpoint.mdAndUp ? 'hero-big-area' : 'hero-small-area'"
    >
      <CoreHeader />
      <section class="slider-section d-flex align-end">
        <div class="slide-box">
          <img src="https://i.postimg.cc/8ctQZN4L/design-1.png" alt="" width="100%">
        </div>

        <v-container>
          <v-carousel
            cycle
            hide-delimiter-background
            hide-delimiters
            :show-arrows="false"
            height="auto"
          >
            <v-carousel-item
              v-for="(slide, i) in slides"
              :key="i"
            >
              <v-sheet color="transparent">
                <v-row
                  class="ma-0 flex-wrap-reverse"
                  align="center"
                  justify="center"
                >
                  <v-col md="6" cols="12">
                    <h2 class="text-h4 my-4 d-flex align-center status">
                      {{ slide.status }}
                      <v-divider class="mx-3" />
                    </h2>
                    <h1 class="text-uppercase font-weight-bold mb-6" :class="$vuetify.breakpoint.mdAndUp ? 'text-h1' : 'text-h2'">
                      {{ slide.title }}
                    </h1>
                    <p class="subtitle-1 mb-16">
                      {{ slide.desc }}
                    </p>

                    <v-btn tile color="black" class="subtitle-1 px-11 py-6 text-capitalize white--text">
                      Shop Now
                    </v-btn>

                    <span class="mx-6 text-h5 pt-4 grey--text text--lighten-1 slide-number">
                      {{ i > 9 ? '': '0' }}{{ i }}
                    </span>
                  </v-col>
                  <v-col md="6" cols="12">
                    <div class="slide-img">
                      <img :src="slide.img" :alt="slide.title" width="100%">
                    </div>
                  </v-col>
                </v-row>
              </v-sheet>
            </v-carousel-item>
          </v-carousel>
        </v-container>
      </section>
    </v-img>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slides: [
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        },
        {
          status: 'New Collection',
          title: 'Jewellery',
          desc: 'Lorem ipsum dolor sit amet consec tetur adipiscing elit elit at felislacinia aptent taciti sociosqu ad litora torquent per conubia nostra',
          img: 'https://i.postimg.cc/yd4HLKMH/slider-img.png'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.hero-big-area { height: 100vh; }
.hero-small-area { height: auto; }
.hero {
  position: relative;

  .slider-section {
    position: relative;

    .slide-box {
      position: absolute;
      bottom: 0;
      left: 0;
      -webkit-transform: translateY(-50%);
      transform: translateY(-50%);
      width: 75px;
    }
    .status {
      .v-divider {
        max-width: 60px !important;
        border: black solid;
        border-width: 1px 0 0 0;
      }
    }
    .slide-number {
      vertical-align: middle;
    }

    .slide-img {
      img {
        vertical-align: middle;
      }
    }
  }
}
</style>
