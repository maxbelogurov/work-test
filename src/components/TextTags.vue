<template>
  <v-container>
    <v-row >
      <v-btn color="primary"
             @click="tagsAlign(true)"
             :disabled="alignLeft">Left</v-btn>
      <v-btn color="primary"
             @click="tagsAlign(false)"
             :disabled="!alignLeft">Justify</v-btn>
    </v-row>
    <v-row>
      <v-col v-for="(tag, i) in myTags"
             :key="i">
        <div>
          <div>
            <v-icon>{{tag.icon}}</v-icon>
          </div>
          <div>{{tag.text}}</div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "TextTags",
  data() {
    return {
      alignLeft: false,
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
    }
  },
  methods: {
    tagsAlign(b) {
      this.alignLeft = b
    }
  }
}
</script>

<style scoped>

</style>