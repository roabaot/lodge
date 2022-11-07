<template>
  <div class="py-12">
    <section class="contact d-flex align-end">
      <div class="contact-box">
        <img src="https://i.postimg.cc/mDy0rB0K/design-2.png" alt="" width="100%">
      </div>

      <v-container>
        <h2 class="text-h4 my-6">
          Contact Us
        </h2>

        <v-row
          class="ma-0 flex-wrap-reverse"
          align="center"
          justify="center"
        >
          <v-col md="6" cols="12">
            <v-form class="mt-4 contact-form">
              <ValidationObserver ref="observer">
                <div>
                  <ValidationProvider
                    v-slot="{ errors }"
                    name="name"
                    rules="required"
                  >
                    <v-text-field
                      v-model="name"
                      solo
                      label="Name"
                      :error-messages="errors"
                    />
                  </ValidationProvider>
                </div>
                <div>
                  <ValidationProvider
                    v-slot="{ errors }"
                    name="email"
                    rules="required|email"
                  >
                    <v-text-field
                      v-model="email"
                      solo
                      label="Email"
                      :error-messages="errors"
                    />
                  </ValidationProvider>
                </div>
                <div>
                  <ValidationProvider
                    v-slot="{ errors }"
                    name="phone"
                    rules="min:3|max:16"
                  >
                    <v-text-field
                      v-model="phone"
                      solo
                      label="Phone"
                      :error-messages="errors"
                    />
                  </ValidationProvider>
                </div>
                <div>
                  <ValidationProvider
                    v-slot="{ errors }"
                    name="message"
                    rules="max:255"
                  >
                    <v-textarea
                      v-model="message"
                      counter="255"
                      solo
                      label="Message"
                      :error-messages="errors"
                    />
                  </ValidationProvider>
                </div>
              </ValidationObserver>

              <div class="mt-10 mb-8">
                <v-btn rounded large class="contact-btn px-12 white--text subtitle-1" :class="$vuetify.breakpoint.mdAndUp ? 'py-6' : ''" @click="onContact">
                  Send
                </v-btn>
              </div>
            </v-form>
          </v-col>
          <v-col md="6" cols="12">
            <div class="fill-height d-flex">
              <iframe
                src="https://www.google.com/maps/embed/v1/place?key=AIzaSyA0s1a7phLN0iaD6-UE7m4qP-z21pH0eSc&q=Eiffel+Tower+Paris+France"
                width="100%"
                :height="$vuetify.breakpoint.mdAndUp ? 500 : 300"
                frameborder="0"
                allowfullscreen
                style="z-index: 14"
              />
            </div>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
import {
  ValidationObserver,
  ValidationProvider,
  setInteractionMode
} from 'vee-validate'
setInteractionMode('eager')
export default {
  components: {
    ValidationProvider,
    ValidationObserver
  },
  data () {
    return {
      name: '',
      email: '',
      phone: '',
      message: ''
    }
  },
  methods: {
    onContact () {
      this.$refs.observer.validate().then((noErrors) => {
        if (noErrors) {
          this.name = ''
          this.email = ''
          this.phone = ''
          this.message = ''
          this.$nuxt.$router.push('/')
          const element = document.getElementById('home')
          element.scrollIntoView({ behavior: 'smooth' })
        }
      })
    }
  }
}
</script>

<style>
.v-application--is-ltr .v-text-field .v-counter, .v-messages__message {
  z-index: 10;
}
</style>

<style lang="scss" scoped>
.contact {
  position: relative;
  .contact-box {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 75px;
    z-index: 0;
  }

  .contact-form {
    .contact-btn {
      background: linear-gradient(to bottom, #f5e47b, #fb930a);
    }
  }
}
</style>
