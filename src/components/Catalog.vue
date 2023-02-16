<template>
        <section class="section_style catalog_position">
            <div class="grey lighten-5 catalog_width catalog_height">
                <v-container class="max-width-conteiner catalog_height">
                    <v-tabs class="catalog_height tabs_position"
            background-color="grey lighten-5"
            slider-color="grey"
          >
            <v-tab
              hide-on-leave
              background-color="#fff"
              color="#fff"
              class="text-capitalize catalog_height fonts"
              @click="toggleTab('fieldOfKnowledge')"
              >Области знаний</v-tab
            >
            <v-tab class="text-capitalize catalog_height fonts" @click="toggleTab('rubrics')">Рубрики</v-tab>
          </v-tabs>
                </v-container>
            </div>
      <v-container class="white lighten-5  max-width-conteiner fonts">
        <div class="grey">
          
        </div>
        <div v-if="variable==='fieldOfKnowledge'">
          <v-row class="my-1">
            <v-col
              v-for="(item, index) in items"
              :key="index"
              class="text-caption py-2 font-weight-medium fonts rubric-fonts"
              lg="3"
              md="4"
              sm="6"
              xl="3"
              cols="12"
            >
              {{ item.title }}
            </v-col>
          </v-row>
        </div>
        <div v-if="variable==='rubrics'">
          <v-row class="my-1">
            <v-col
              v-for="(item, index) in items"
              :key="index"
              class="text-caption py-2 font-weight-medium fonts rubric-fonts"
              lg="3"
              md="4"
              sm="6"
              xl="3"
              cols="12"
            >
              Что-то отличное от {{ item.title }}
            </v-col>
          </v-row>
        </div>
      </v-container>
      <div class="grey lighten-5 catalog_width catalog_height fonts">
          <v-conteiner class="max-width-conteiner fonts catalog-more_rubrics px-3">
            <a
            href="/"
            class="text-decoration-none grey--text font-weight-medium"
          >
          <div>
            Показать все варианты</div>
        
          </a>
        </v-conteiner>
        </div>
    </section>
</template>

<script>
import { RUBRICS } from '@/const/const'
export default {
    data: () => ({
    items: RUBRICS,
    variable : 'fieldOfKnowledge'
  }),
  methods: {
   toggleTab(tab) {
      this.variable = tab
      return
    },
  },
}
</script>

<style>
.section_style {
    background-color: rgb(255, 255, 255);
    width: 100%;
}
.catalog_position {
  position: fixed;
  z-index: 2;
}
.catalog_width {
    width: auto;
    background-color: antiquewhite;
}
.catalog_height {
    height: 48px;
}
.tabs_position {
    position: absolute;
    top: 0;
}
.rubric-fonts {
  font-size: 13px;
  color: black;
  letter-spacing: 0.195px;
}
.catalog-more_rubrics {
    display: block;
    margin-left: auto;
    margin-right: auto;
}
</style>