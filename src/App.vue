<template>
  <v-app>
    <v-container fluid="fluid" class="my-3">
      <v-row class="pa-3">
        <v-btn-toggle>
          <v-btn color="primary"
                 @click="tagsAlign(true)"
                 :disabled="this.alignLeft"> Left
          </v-btn>
          <v-btn color="primary"
                 @click="tagsAlign(false)"
                 :disabled="!this.alignLeft">Justify
          </v-btn>
        </v-btn-toggle>
      </v-row>
      <text-tags v-bind:Tags="myTags"
                 v-bind:Align="justify"></text-tags>
      <v-row class="pa-3">
        <p class="mt-3">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
          labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore
          eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt
          mollit anim id est laborum.</p>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import TextTags from "@/components/TextTags";

export default {
  name: 'App',
  components: {
    TextTags,
  },
  data: () => ({
    alignLeft: true,
    justify: 'start',
    myTags: [
      {
        text: 'Площадка для парковки',
        icon: 'mdi-alert'
      },
      {
        text: 'Дом с красивыми видом',
        icon: 'mdi-bookmark'
      },
      {
        text: 'Вторичка'
      },
      {
        text: 'Квартира'
      },
      {
        text: 'Загородный дом',
        icon: 'mdi-lightbulb'
      },
      {
        text: 'С видом на море',
        icon: 'mdi-atv'
      },
      {
        text: 'Офисное здание',
        icon: 'mdi-arrow-down-bold'
      }
    ]
  }),
  methods: {
    tagsAlign(b) {
      this.alignLeft = b
      b ? this.justify = 'start' : this.justify = 'space-between'
    }
  },
};
</script>
