<template>
  <v-app light>
    <v-toolbar class="white">
      <v-toolbar-side-icon>
        <img :src="imageLink.logo" alt="Mamá Coneja" height="75px" />
      </v-toolbar-side-icon>
      <v-toolbar-title class="mx-0" v-text="title"></v-toolbar-title>
      <!-- <p>Beta</p> -->
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat>Facebook</v-btn>
        <v-btn flat class="pink lighten-3">Whatsapp</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <section>
        <v-parallax :src="imageLink.sub_main" height="600">
          <v-layout column align-center justify-center class="white--text">
            <h1
              class="white--text mb-2 display-1 text-xs-center"
              style="font-weight: 900; text-shadow: 3px 2px #000000"
            >---</h1>
            <div
              class="white--text subheading mb-3 text-xs-center"
              style="font-weight: 900; text-shadow: 2px 2px #000000"
            >---</div>
            <v-btn class="blue lighten-2 mt-5" dark large href="#">---</v-btn>
          </v-layout>
        </v-parallax>
      </section>

      <section>
        <v-layout column wrap class="my-5" align-center>
          <v-flex xs12 sm4 class="my-3">
            <div class="text-xs-center">
              <h2 class="headline">---</h2>
              <span class="subheading">--</span>
            </div>
          </v-flex>
          <v-flex xs12>
            <v-container grid-list-xl>
              <v-layout row wrap align-center>
                <v-flex xs12 md4>
                  <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                      <v-icon x-large class="blue--text text--lighten-2">public</v-icon>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                      <div class="headline text-xs-center">Manualidades</div>
                    </v-card-title>
                    <v-card-text>---</v-card-text>
                  </v-card>
                </v-flex>
                <v-flex xs12 md4>
                  <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                      <v-icon x-large class="blue--text text--lighten-2">flash_on</v-icon>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                      <div class="headline">Enseñanza</div>
                    </v-card-title>
                    <v-card-text>---</v-card-text>
                  </v-card>
                </v-flex>
                <v-flex xs12 md4>
                  <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                      <v-icon x-large class="blue--text text--lighten-2">share</v-icon>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                      <div class="headline text-xs-center">Comparte</div>
                    </v-card-title>
                    <v-card-text>---</v-card-text>
                  </v-card>
                </v-flex>
              </v-layout>
            </v-container>
          </v-flex>
        </v-layout>
      </section>

      <section>
        <v-parallax :src="imageLink.main" height="380">
          <v-layout column align-center justify-center>
            <div
              class="headline white--text mb-3 text-xs-center"
            >¿Te gustaría aprender a tejer adorables muñecos?</div>
            <em>Anímate y contáctame, pronto aprenderás a tejer.</em>
            <v-btn
              class="blue lighten-2 mt-5"
              dark
              large
              href="https://www.facebook.com/ManualidadesMamaConeja/"
            >Visitanos</v-btn>
          </v-layout>
        </v-parallax>
      </section>

      <section>
        <v-container grid-list-md>
          <v-layout row wrap>
            <v-flex xs12 text-xs-center class="mt-5">
              <div class="headline">Quieres contactarnos?</div>
              <br />
              <div>
                Encuentranos en Facebook
                (link facebook) o escribenos en Whatsapp (link)
              </div>
            </v-flex>
            <v-flex xs8 offset-xs2>
              <v-card class="elevation-0 transparent">
                <v-card-text>
                  <v-flex xs12 v-if="!subscribed">
                    <v-text-field
                      box
                      label="Email"
                      :rules="emailRules"
                      v-model="email"
                      hint="Ingresa tu Email!"
                      persistent-hint
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 class="text-xs-center" v-if="!subscribed">
                    <v-btn class="blue lighten-2 mb-5" dark large @click="subscribe">Aun toque</v-btn>
                  </v-flex>
                  <v-flex xs12 class="text-xs-center" v-if="subscribed">
                    <v-btn class="green lighten-2 mb-5" dark large>Bienvenido a bordo!</v-btn>
                  </v-flex>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </section>

      <section>
        <v-parallax :src="imageLink.social_cover" height="380">
          <v-layout column align-center justify-center>
            <div class="headline white--text mb-3 text-xs-center">Diseños diferentes.</div>
          </v-layout>
          <v-layout justify-space-around justify-center>
            <v-icon x-large dark>fab fa-facebook-f</v-icon>

            <v-icon x-large dark>fab fa-twitter</v-icon>

            <v-icon x-large dark>fab fa-reddit-alien</v-icon>

            <v-icon x-large dark>fab fa-instagram</v-icon>

            <v-icon x-large dark>fab fa-discord</v-icon>
          </v-layout>
        </v-parallax>
      </section>

      <section>
        <v-container grid-list-xl>
          <v-layout row wrap justify-center class="my-5">
            <v-flex xs12 sm4>
              <v-card class="elevation-0 transparent">
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline">Informacion</div>
                </v-card-title>
                <v-card-text>---</v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 sm4 offset-sm1>
              <v-card class="elevation-0 transparent">
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline">----</div>
                </v-card-title>
                <v-card-text>---</v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </section>

      <section>
        <v-container>
          <v-layout>
            <v-flex xs12 class="text-xs-center">
              <img height="200px" :src="imageLink.logo" />
            </v-flex>
          </v-layout>
        </v-container>
      </section>

      <v-footer class="blue darken-2">
        <v-layout row wrap align-center>
          <v-flex xs12 class="text-xs-center">
            <div class="white--text ml-3">
              Realizado con
              <v-icon class="red--text">favorite</v-icon>usando
              <a class="white--text" href="https://vuetifyjs.com" target="_blank">Vuetify</a>
            </div>
          </v-flex>
        </v-layout>
      </v-footer>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      title: "Mamá Coneja",
      imageLink: {
        logo:
          "https://scontent.fgdl3-1.fna.fbcdn.net/v/t1.0-9/58895045_2102995976671778_820388442012647424_n.jpg?_nc_cat=103&_nc_oc=AQl3OAl8zsWQFOza3X-GcjFjA81BpGTAr-cvGYn8erlRltooRneSUExQY4cTuRgIdak&_nc_ht=scontent.fgdl3-1.fna&oh=d22f8986f52d67fb8750a14d22c482d3&oe=5DA54E11",
        main:
          "https://scontent.fgdl3-1.fna.fbcdn.net/v/t1.0-9/59464707_2103011323336910_2931360285266542592_o.jpg?_nc_cat=106&_nc_oc=AQlSuIhlh5mzoM0I-L3O3eoe2lbFaI8wXVYkJjL3zG6ZgXLENV1z0VDhuVfhSovD4x4&_nc_ht=scontent.fgdl3-1.fna&oh=935bffe190a9344cae8ab51b5c8eec45&oe=5DBD8B60",
        sub_main:
          "https://i.pinimg.com/originals/91/27/77/912777a070c633348768309d900d8255.jpg",
                  social_cover:
          "https://scontent.fgdl3-1.fna.fbcdn.net/v/t1.0-9/59602897_2103068319997877_2457549320056995840_o.jpg?_nc_cat=110&_nc_oc=AQlAp3oJw4YBvEk_x_nGRSRK7vsOY2iu47dBjLdT7Q2SC5K1NvEFpXzBGWoBpqrdERs&_nc_ht=scontent.fgdl3-1.fna&oh=8da8e55a8f9e317b94d838d8818bb071&oe=5DBC5D08"
      },
      email: "",
      emailRules: [
        v => {
          return !!v || "Email Requerido";
        },
        v =>
          /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
          "Email deve de ser valido"
      ],
      subscribed: false
    };
  },
  methods: {
    subscribe: function() {
      this.subscribed = !this.subscribed;
    }
  },

  computed: {
    imgHeight: function() {
      var offset = 320;
      //console.log("new image height is " + (this.pageHeight - offset));
      return this.pageHeight - offset;
    }
  },
  mounted: function() {
    this.calculateHeight();
  }
};
</script>

<style scoped>
.finedTitle {
  font-weight: 900;
  text-shadow: 2px 2px #000000;
}

.social-icon {
  font-size: 21px;
  color: white;
}
</style>
