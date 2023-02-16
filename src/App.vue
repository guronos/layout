<template>
  <v-app>
    <div class="nav-bar">
      <v-app-bar flat height="72" color="#fff" class="py-1">
        <div class="max-width-conteiner nav-bar_position">
          <v-container
            class="d-flex flex-row white lighten-5 justify-space-between align-center menu_wrap fonts px-2"
          >
            <div class="logo-block">
              <a href="/"><img src="./assets/logo.svg" width="142px" /></a>
            </div>
            <div class="grey lighten-5 d-flex align-center search-width">
              <img src="./assets/search.svg" class="px-3" />
              <input
                type="text"
                placeholder="Поиск"
                class="fonts fonts-medium_size"
              />
            </div>
            <div class="menu d-flex align-center menu">
              <div>
                <button
                  class="pa-0 text-decoration-none text-capitalize fonts-medium_size"
                  @click="togge()"
                >
                  <span class="header_fonts px-2"
                    ><img
                    style="margin-bottom: -2px;"
                      src="@/assets/catalogIcon.svg"
                      height="14px"
                      width="14px"
                  /></span>
                  Каталог
                </button>
              </div>
              <div class="px-4">
                <a
                  href="/"
                  class="text-decoration-none black--text fonts-medium_size px-2"
                  >Стать автором</a
                >
              </div>

              <div>
                <a href="/" class="text-decoration-none black--text fonts-medium_size"
                  >Вход</a
                >
              </div>
            </div>
          </v-container>
        </div>
        <br />
      </v-app-bar>
      <v-divider />
    </div>
    <v-main>
      <catalog v-if="this.switch" />
      <v-container class="max-width-conteiner fonts px-5 py-1">
        <v-container>
          <template v-for="item in items">
            <a
              href="/"
              class="text-decoration-none black--text fonts-medium_size fonts_letter-spacing catalog-bar"
              v-if="item.showInMainMenu"
              :key="item.title"
            >
              {{ item.title }}
            </a>
          </template>
        </v-container>
      </v-container>
      <div class="backgraund_blue mt-1">
        <v-container
          class="mb-10 max-width-conteiner fonts px-8 fonts-medium_size fonts_letter-spacing"
        >
          <a href="/" class="white--text"
            >Научно-образовательный портал «Большая российская энциклопедия»</a
          >
        </v-container>
      </div>
      <v-container class="max-width-conteiner fonts px-8">
        <div>
          <h3 class="fonts-big_size pt-14">Научные отрасли</h3>
        </div>
        <div class="main-block pt-5 mainCardsBlock">
          <v-row>
            <v-col lg="3" xl="3" md="12" sm="12" cols="12">
              <div to="/" class="overflow-hidden card-style card-mini mb-6">
                <div class="img1"></div>
                <div class="card-mini_text pt-4 px-1">
                  <div class="fonts_header px-2">
                    {{ publications[0].title }}
                  </div>
                  <div class="fonts_text px-2 card_overflow">
                    {{ publications[0].text }}
                  </div>
                </div>
              </div>
              <div to="/" class="overflow-hidden card-style card-mini">
                <div class="img2"></div>
                <div class="card-mini_text pt-4 px-1">
                  <div class="fonts_header px-2">
                    {{ publications[2].title }}
                  </div>
                  <div class="fonts_text px-2 card_overflow">
                    {{ publications[2].text }}
                  </div>
                </div>
              </div>
            </v-col>
            <v-col lg="6" xl="6" md="12" sm="12" cols="12" class="pl-4">
              <div
                to="/"
                class="overflow-hidden d-flex flex-column card-style card-big"
              >
                <div></div>
                <div class="img3"></div>
                <div class="card-big_text_padding">
                  <div class="card-big-header_fonts">
                    {{ publications[1].title }}
                  </div>
                  <div class="fonts-medium_size fonts_letter-spacing card-big_fonts">
                    {{ publications[1].text }}
                  </div>
                </div>
              </div>
            </v-col>
            <v-col lg="3" xl="3" md="12" sm="12">
              <div class="d-flex flex-column pl-5 posts_width">
               
                  <div v-for="post, index in posts" :key="index">
                    <div class="px-2 py-3">
                      <div class="fonts_header">
                        {{ post.title }}
                      </div>
                      <div class="posts_overflow fonts fonts_text post-text_size">
                        {{ post.text }}
                      </div>
                    </div>
                    <v-divider v-if="index < 4" />
                  </div>
              </div>
            </v-col>
          </v-row>
        </div>
        <div class="long-block_border my-10">
          <v-img
            src="./assets/buckgroundCard.webp"
            class="white--text align-center long-block_border"
            height="408px"
          >
            <v-card
              color="rgba(0, 0, 0, 0.7)"
              height="408px"
              class="px-14 py-16"
            >
              <div class="long-block">
                <v-chip
                  class="grey--text mx-4"
                  color="rgba(256, 256, 256)"
                  small
                  label
                >
                  Научные теории, концепции, гипотезы, модели
                </v-chip>
                <v-card-title class="white--text">
                  <h1 class="long-block-fonts_header">Теория Большого взрыва</h1>
                </v-card-title>
                <v-card-text class="white--text long-block-text">
                  {{ BIG_EXPLOSION }}
                </v-card-text>
              </div>
            </v-card>
          </v-img>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
import Catalog from "./components/Catalog.vue";
import { RUBRICS, PUBLIC_ELEM, MINI_POSTS, BIG_EXPLOSION } from "./const/const";
export default {
  name: "App",
  components: {
    Catalog,
  },

  data: () => ({
    items: RUBRICS,
    publications: PUBLIC_ELEM,
    posts: MINI_POSTS,
    switch: false,
    BIG_EXPLOSION,
  }),
  methods: {
    togge() {
      if (this.switch) {
        this.switch = false;
      } else {
        this.switch = true;
      }
    },
  }
};
</script>
<style>
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

.max-width-conteiner {
  max-width: 1224px;
}
.search-width {
  min-width: 601px;
  height: 36px;
  padding: 6px 12px;
  box-sizing: border-box;
  border-radius: 5px;
}
.fonts {
  font-family: "HelveticaMac", system-ui, "Segoe UI", Roboto, Arial, "Noto Sans",
    "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
    "Segoe UI Symbol", "Noto Color Emoji";
}
.fonts_header {
  font-size: 14px;
  font-weight: 700;
  color: rgb(0, 0, 0);
}
.fonts_text {
  color: rgb(102, 102, 102);
  font-size: 12px;
  line-height: 24px;
}
.fonts-medium_size {
  font-size: 14px;
}
.card-style {
  box-shadow: rgba(0, 0, 0, 0.08) 0px 0px 24px 0px;
  border-radius: 5px;
}
.backgraund_blue {
  background-color: #436ee6;
  height: 48px;
}
.main-block {
  max-height: 600px;
  margin-bottom: 72px;
}
.card-mini {
  height: 288px;
  max-width: 276px;
}
.card-big {
  width: 576px;
  height: 600px;
}
.menu_wrap {
  width: 1176px;
  height: 42px;
}
.nav-bar_position {
  margin-left: auto;
  margin-right: auto;
}
.fonts-big_size {
  font-size: 20px;
}
.card_overflow {
  height: 48px;
  overflow: hidden;
  text-overflow: clip;
  text-transform: none;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  display: -webkit-box;
}
.card-mini_text {
  width: 252px;
  height: 72px;
}
.logo-block {
  width: 164px;
}
.menu {
  height: 24px;
  width: 272px;
  margin-left: 20px;
  padding-bottom: 8px;
  margin-right: -21px;
  letter-spacing: 0.35px;
}
.fonts_letter-spacing {
  letter-spacing: 0.35px;
}
.catalog-bar {
  margin-right: 22px;
}
.nav-bar {
  position: sticky;
  z-index: 12;
  top: 0;
}
.card-big_fonts {
  line-height: 24px;
  margin-top: 12px;
  color: rgb(102, 102, 102);
}
.card-big-header_fonts {
  line-height: 24px;
  font-size: 18px;
  font-weight: 700;
}
.card-big_text_padding {
  padding: 24px;
}
.post-text_size {
  width: 246px;
  height: 72px;
}
.posts_width {
  width: 270px;
}
.long-block {
  width: 726px;
  height: 264px;
  overflow: hidden;
  text-overflow: clip;
  text-transform: none;
}
.long-block-text {
  height: 168px;
  overflow: hidden;
  text-overflow: clip;
  text-transform: none;
  letter-spacing: 0.35px;
  line-height: 24px;
  font-size: 14px;
  margin-top: 12px;
}
.long-block_border {
  border-radius: 9px;
}
.long-block-fonts_header {
  font-size: 36px;
}
.posts_overflow {
  overflow: hidden;
  text-overflow: clip;
  text-transform: none;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  display: -webkit-box;
}
</style>
