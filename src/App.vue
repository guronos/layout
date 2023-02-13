<template>
  <v-app app>
    <v-app-bar app flat height="72" color="#fff" class="px-0">
      <div class="maxWidthConteiner tet">
      <v-container
        class="
          d-flex
          flex-row
          white
          lighten-5
          justify-space-between
          align-center
          wrapHead
          fonts
          px-0
        "
      >
      
        <div class="logo">
          <a href="/"><img src="./assets/logo.svg" /></a>
        </div>
        <div class="grey lighten-5 d-flex align-center searchWidth">
          <img src="./assets/search.svg" />
          <input type="text" placeholder="Поиск" />
        </div>
        <div class="menu d-flex align-center">
          <div>
            <v-btn
              class="pa-0 text-decoration-none text-capitalize headerFonts"
              color="gray"
              plain
              @click="togge()"
              >Каталог</v-btn
            >
          </div>
          <div class="px-4">
            <a href="/" class="text-decoration-none black--text headerFonts"
              >Стать автором</a
            >
          </div>

          <div>
            <a href="/" class="text-decoration-none black--text headerFonts">Вход</a>
          </div>
        </div>
       </v-container>
      </div>
     
    </v-app-bar>
    <v-main>
      <v-divider />
      <catalog v-if="this.switch" />
      <v-container class="maxWidthConteiner fonts">
        <v-container>
          <template v-for="item in items">
          <a href="/" class="text-decoration-none black--text pr-4 headerFonts" v-if="item.showInMainMenu" :key="item.title">
            {{            item.title          }}
          </a>
          </template>
        <!-- <div v-for="(item, index) in items" v-if="index % 4 == 0" :key="index" class="pr-2 d-inline-flex"
          ></div -->
        </v-container>
      </v-container>
      <div class="blueBackgraund">
        <v-container class="mb-10 maxWidthConteiner fonts">
          <a href="/" class="white--text"
            >Научно-образовательный портал "большая Российская энциклопедия"</a
          >
        </v-container>
      </div>
      <v-container class="maxWidthConteiner fonts">
        <div>
          <h3>Научные отрасли</h3>
        </div>
        <div class="mainPostBlock">
          <v-row>
            <v-col lg="3" xl="3" md="12" sm="12" cols="12">
              <v-card
                to="/"
                class="overflow-hidden cardStyle miniBlock mb-6"
              >
                <div class="img1"></div>
                <div class="fontsHeader px-2">
                  {{ publications[0].title }}
                </div>
                <v-card-text class="fontsText px-2">
                  {{ publications[0].text }}
                </v-card-text>
              </v-card>
              <div
                
                to="/"
                class="overflow-hidden cardStyle miniBlock"
              >
                <!-- <v-img src="./assets/card2.webp"></v-img> -->
                <div class="img2"></div>
                <div class="fontsHeader px-2">
                  {{ publications[2].title }}
                </div>
                <v-card-text class="fontsText px-2">
                  {{ publications[2].text }}
                </v-card-text>
              </div>
            </v-col>
            <v-col lg="6" xl="6" md="12" sm="12" cols="12">
              <v-card
                to="/"
                class="overflow-hidden d-flex flex-column cardStyle bigCardBlock"
              >
                <div>
                </div>
                <div class="img3"></div>
                <div>
                  <div class="fontsHeader">
                    {{ publications[1].title }}
                  </div>
                  <v-card-text class="fontsText">
                    {{ publications[1].text }}
                  </v-card-text>
                </div>
              </v-card>
            </v-col>
            <v-col lg="3" xl="3" md="12" sm="12">
              <v-card flat :height="heightPosts" class="d-flex flex-column">
                <card flat class="overflow-hidden px-2" to="/">
                  <div class="fontsHeader">
                    {{ posts[0].title }}
                  </div>
                  <div
                    class="
                      overflow-hidden
                      fonts
                      fontsText
                    "
                  >
                  {{ posts[0].text }}
                  </div>
                </card>
                <v-divider class="my-2" />
                <card flat class="overflow-hidden px-2" to="/">
                  <div class="fontsHeader">
                    {{ posts[1].title }}
                  </div>
                  <div
                    class="
                    overflow-hidden
                      fonts
                      fontsText
                    "
                  >
                  {{ posts[1].text }}
                  </div>
                </card>
                <v-divider class="my-2" />
                <card flat class="overflow-hidden px-2" to="/">
                  <div class="fontsHeader">
                    {{ posts[2].title }}
                  </div>
                  <div
                    class="
                    overflow-hidden
                      fonts
                      fontsText
                    "
                  >
                  {{ posts[2].text }}
                  </div>
                </card>
                <v-divider class="my-2" />
                <card flat class="overflow-hidden px-2" to="/">
                  <div class="fontsHeader">
                    {{ posts[3].title }}
                  </div>
                  <div
                    class="
                    overflow-hidden
                      fonts
                      fontsText
                    "
                  >
                  {{ posts[3].text }}
                  </div>
                </card>
                <v-divider class="my-2" />
                <card flat class="overflow-hidden px-2" to="/">
                  <div class="fontsHeader">
                    {{ posts[4].title }}
                  </div>
                  <div
                    class="
                    overflow-hidden
                      fonts
                      fontsText
                    "
                  >
                  {{ posts[4].text }}
                  </div>
                </card>
                <v-divider class="my-2" />
              </v-card>
            </v-col>
          </v-row>
        </div>
        <v-card class="my-10" flat>
          <v-img
            src="./assets/buckgroundCard.webp"
            class="white--text align-center"
            height="408px"
          >
            <v-card
              color="rgba(0, 0, 0, 0.7)"
              height="408px"
              class="px-12 py-10"
            >
              <v-card-text>
                <v-chip
                  class="grey--text"
                  color="rgba(256, 256, 256)"
                  small
                  label
                >
                  Научные теории, концепции, гипотезы, модели
                </v-chip>
              </v-card-text>
              <v-card-title class="white--text">
                <h1>Теория Большого взрыва</h1>
              </v-card-title>
              <v-card-text class="white--text">
                {{BIG_EXPLOSION}}
              </v-card-text>
            </v-card>
          </v-img>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Catalog from './components/Catalog.vue';
import { RUBRICS, PUBLIC_ELEM, MINI_POSTS, BIG_EXPLOSION } from './const/const'

export default {
  name: "App",

  components: {
    Catalog
  },

  data: () => ({
    items: RUBRICS,
    publications : PUBLIC_ELEM,
    posts: MINI_POSTS,
    switch: false,
    BIG_EXPLOSION
  }),
  methods: {
    togge() {
      if (this.switch) {
        this.switch = false;
      } else {
        this.switch = true;
      }
    },
    imagePach(pach) {
      return require(`@/assets/${pach}`);
    },
  },
  computed: {
    heightFull() {
      if (
        this.$vuetify.breakpoint.name === "xs" ||
        this.$vuetify.breakpoint.name === "sm" ||
        this.$vuetify.breakpoint.name === "md"
      ) {
        console.log(this.$vuetify.breakpoint.name)
        return 648;
      } else {
        return 648;
      }
    },
    heightminiblock() {
      if (
        this.$vuetify.breakpoint.name === "xs" ||
        this.$vuetify.breakpoint.name === "sm" ||
        this.$vuetify.breakpoint.name === "md"
      ) {
        return 648;
      } else {
        return 316;
      }
    },heightPosts() {
      if (
        this.$vuetify.breakpoint.name === "xs" ||
        this.$vuetify.breakpoint.name === "sm" ||
        this.$vuetify.breakpoint.name === "md"
      ) {
        return 'auto';
      } else {
        return 648;
      }
    }
  },
};
</script>
<style>
.smallDescription {
  height: 85px;
}

.img1 {
  background-image: url("./assets/card1.webp");
  height: 192px;
  background-size: cover;
}

.img2 {
  background-image: url("./assets/card3.webp");
  height: 192px;
  background-size: cover;
}

.img3 {
  background-image: url("./assets/card2.webp");
  height: 396px;
  width: 576px;
  background-size: cover;
}
.rubricsMenu{
  position: fixed;
  z-index: 2;
}
.maxWidthConteiner {
  max-width: 1224px;
}
.searchWidth {
  min-width: 651px;
  height: 36px;
  border-radius: 5px;
}
.fonts {
  font-family:"HelveticaMac",system-ui,"Segoe UI",Roboto,Arial,"Noto Sans","Liberation Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
}
.fontsHeader{
font-size: 14px;
font-weight: 700;
color: rgb(0, 0, 0);
}
.fontsText{
  color: rgb(102, 102, 102);
  font-size: 12px;
  line-height: 24px;
}
.headerFonts {
  font-size: 14px;
}
.cardStyle {
  box-shadow:rgba(0,0,0,.08) 0px 0px 24px 0px;
}
.blueBackgraund {
  background-color: #436ee6;
}
.mainPostBlock{
  max-height: 600px;
  margin-bottom: 20px;
}
.miniBlock{
  max-height: 288px;
  max-width: 276px;
}
.bigCardBlock {
  width: 576px;
height:600px;
}
.wrapHead {
  width: 1176px;
  height: 42px;
}
.tet{
  margin-left: auto;
    margin-right: auto;
}
</style>
