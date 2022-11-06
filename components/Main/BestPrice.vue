<template>
  <v-container class="py-12">
    <div class="d-flex justify-center flex-wrap">
      <template v-for="(item, i) in items">
        <v-hover v-slot="{ hover }" :key="i">
          <v-card
            :outlined="hover ? false : true"
            :class="{ 'on-hover card-onhover': hover }"
            class="card-price ma-2"
            width="300"
            @click.stop=""
          >
            <v-card-title class="status subtitle-1 text-uppercase">
              Best Price
            </v-card-title>
            <div class="img-box">
              <img
                :src="item.img"
                height="125"
                class="text-center"
              />
            </div>
            <v-card-title class="pt-0">
              {{ item.title }}
            </v-card-title>
          </v-card>
        </v-hover>
      </template>
    </div>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'BRACELET',
          img: 'img/i-1.png'
        },
        {
          title: 'RING',
          img: 'img/i-2.png'
        },
        {
          title: 'EARINGS',
          img: 'img/i-3.png'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.card-onhover {
  box-shadow: 0px 2px 1px 0px rgb(0 0 0 / 20%), 0px 10px 30px 4px rgb(0 0 0 / 14%), 0px 0px 2px 0px rgb(0 0 0 / 12%) !important
}
.card-price {
  .status {
    color: #fbb534;
  }
  .img-box {
    width: 100%;
    display: flex;
    -webkit-box-pack: center;
    justify-content: center;
  }
}
</style>
