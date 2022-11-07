<template>
  <div class="grey lighten-4 py-16">
    <v-container>
      <h2 class="text-h4 pb-12">
        Our Jewellery Price
      </h2>

      <div class="d-flex justify-center flex-wrap pb-12">
        <template v-for="(item, i) in items">
          <v-hover v-slot="{ hover }" :key="i">
            <v-card
              :elevation="hover ? 12 : 2"
              :class="{ 'on-hover': hover }"
              class="card-price ma-2 text-center"
              width="300"
              @click.stop=""
            >
              <v-card-title class="headline justify-center">
                {{ item.title }}
              </v-card-title>
              <div class="img-box">
                <img
                  :src="item.img"
                  height="125"
                />
              </div>
              <v-card-title class="headline font-weight-bold pt-0 justify-center">
                $<span class="price">{{ item.price }}</span>
              </v-card-title>
              <v-card-actions class="title justify-center">
                <v-btn outlined tile class="font-weight-bold text-capitalize">Buy Now</v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </template>
      </div>

      <div class="text-center">
        <v-btn tile class="black white--text subtitle-1 text-capitalize px-10 py-5">See More</v-btn>
      </div>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'Diamond Ring',
          img: 'https://i.postimg.cc/15xVq51d/p-1.png',
          price: '1399'
        },
        {
          title: 'Wedding Ring',
          img: 'https://i.postimg.cc/X7SYyz6y/i-1.png',
          price: '699'
        },
        {
          title: 'Golden Earings',
          img: 'https://i.postimg.cc/zXmG9wN5/i-3.png',
          price: '299'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.card-price {
  .price {
    color: #fbb534;
  }
}
</style>
