<template>
  <v-footer padless color="#363636">
    <v-container class="pt-0">
      <div class="info-section">
        <v-row justify="center">
          <v-col md="3" cols="12" class="pt-0">
            <div class="info-logo white d-flex justify-center align-end" :class="!$vuetify.breakpoint.mdAndUp ? 'mx-auto' : ''">
              <img src="img/logo.png" alt="" width="50">
              <span class="text-h4 ml-2">LODGE</span>
            </div>
          </v-col>
          <v-col md="3" cols="12">
            <div class="info-contact" :class="!$vuetify.breakpoint.mdAndUp ? 'text-center py-5' : ''">
              <v-btn text class="white--text">
                <img src="img/location.png" alt="">
                <span class="mx-2 subtitle-1">Address</span>
              </v-btn>
            </div>
          </v-col>
          <v-col md="3" cols="12">
            <div class="info-contact" :class="!$vuetify.breakpoint.mdAndUp ? 'text-center py-5' : ''">
              <v-btn text class="white--text">
                <img src="img/phone.png" alt="">
                <span class="mx-2 subtitle-1">+235 123344556</span>
              </v-btn>
            </div>
          </v-col>
          <v-col md="3" cols="12">
            <div class="info-contact" :class="!$vuetify.breakpoint.mdAndUp ? 'text-center py-5' : ''">
              <v-btn text class="white--text">
                <img src="img/mail.png" alt="">
                <span class="mx-2 subtitle-1">demo@gmail.com</span>
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </div>
      <div class="info-form">
        <div class="text-center">
          <h5 class="my-5 info-heading text-h6 white--text">
            NEWSLETTER
          </h5>
        </div>
        <div class="info-email mx-auto">
          <label class="d-block grey--text text--darken-1 subtitle-1 mb-1">
            Enter Your Email
          </label>
          <v-text-field
            background-color="white"
            outlined
            class="info-email-input"
            dense
          />
        </div>
        <div class="info-subscribe text-center">
          <v-btn class="py-3 px-16 text-uppercase mt-4 white--text subtitle-1" large rounded>
            subscribe
          </v-btn>
        </div>
      </div>
      <div class="info-follow pt-6">
        <div class="text-center">
          <h5 class="my-5 info-heading text-h6 white--text">
            FOLLOW US
          </h5>
        </div>
        <div class="info-website mx-auto">
          <div class="text-center py-3">
            <v-btn icon class="mx-1">
              <img src="img/fb.png" alt="facebook">
            </v-btn>
            <v-btn icon class="mx-1">
              <img src="img/twitter.png" alt="facebook">
            </v-btn>
            <v-btn icon class="mx-1">
              <img src="img/linkedin.png" alt="facebook">
            </v-btn>
            <v-btn icon class="mx-1">
              <img src="img/insta.png" alt="facebook">
            </v-btn>
          </div>
          <div class="mx-6">
            <v-divider class="white" />
            <div class="white--text text-center subtitle-1 pt-4 grey--text text--darken-1">
              © 2022 All Rights Reserved By Ahmed Al-akbari
            </div>
          </div>
        </div>
      </div>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">
.info-section {
  .info-logo {
    width: 200px;
    padding: 100px 10px 45px 10px;
    border-radius: 0 0 50px 50px;
  }
  .info-contact {
    padding: 115px 10px 45px 10px;
    .v-btn {
      text-transform: unset;
      &:hover::before {
        opacity: 0;
      }
    }
  }
}
.info-heading {
  position: relative;
  &::before {
    content: "";
    width: 45px;
    height: 5px;
    position: absolute;
    bottom: -8px;
    left: 50%;
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
    border-radius: 5px;
    background-color: #f8bf46;
  }
}
.info-form {
  .info-email {
    max-width: 500px;
    .info-email-input {
      fieldset {
        border: none !important;
      }
    }
  }
  .info-subscribe {
    .v-btn {
      background: linear-gradient(to bottom, #f5e47b, #fb930a);
    }
  }
}
.info-follow {
  .info-website {
    max-width: 500px;
  }
}
</style>
