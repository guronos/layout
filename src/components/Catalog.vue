<template>
        <section class="sectionStyle rubricsMenu">
            <div class="grey lighten-5 maxWidthBlock maxHeight">
                <v-container class="maxWidthConteiner maxHeight">
                    <v-tabs class="maxHeight positionTabs"
            background-color="grey lighten-5"
            slider-color="grey"
          >
            <v-tab
              hide-on-leave
              background-color="#fff"
              color="#fff"
              class="text-capitalize maxHeight fonts"
              @click="toggleTab('fieldOfKnowledge')"
              >Области знаний</v-tab
            >
            <v-tab class="text-capitalize maxHeight fonts" @click="toggleTab('rubrics')">Рубрики</v-tab>
          </v-tabs>
                </v-container>
            </div>
      <v-container class="white lighten-5  maxWidthConteiner fonts">
        <div class="grey maxWidth">
          
        </div>
        <div v-if="variable==='fieldOfKnowledge'">
          <v-row class="my-1">
            <v-col
              v-for="(item, index) in items"
              :key="index"
              class="text-caption py-2 font-weight-medium fonts rubricFontSize"
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
              class="text-caption py-2 font-weight-medium fonts rubricFontSize"
              lg="3"
              md="4"
              sm="6"
              xl="3"
              cols="12"
            >
              {{ item.title }}+1
            </v-col>
          </v-row>
        </div>
      </v-container>
      <div class="grey lighten-5 maxWidthBlock maxHeight fonts">
          <v-conteiner class="maxWidthConteiner fonts showRubrics px-3">
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
.sectionStyle {
    background-color: rgb(255, 255, 255);
    width: 100%;
    
}
.maxWidthBlock {
    width: auto;
    background-color: antiquewhite;
}
.maxHeight {
    height: 48px;
}
.positionTabs {
    position: absolute;
    top: 0;
}
.rubricFontSize {
  font-size: 13px;
  color: black;
}
.showRubrics {
    display: block;
    margin-left: auto;
    margin-right: auto;
}
</style>