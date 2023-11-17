<template>
  <v-container>
    <v-row class="py-3">
      <v-btn-toggle>
      <v-btn color="primary"
             @click="tagsAlign(true)"
             :disabled="alignLeft">Left</v-btn>
      <v-btn color="primary"
             @click="tagsAlign(false)"
             :disabled="!alignLeft">Justify</v-btn>
      </v-btn-toggle>
    </v-row>
    <v-row :justify="justify">
      <v-col v-for="(tag, i) in myTags"
             :key="i"
              class="col-auto ma-1 tag" bordered>
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
    }
  },
  methods: {
    tagsAlign(b) {
      this.alignLeft = b
      b ? this.justify = 'start' : this.justify = 'space-between'
      // this.justify = b ? 'start' : 'space-between'
    }
  }
}
</script>

<style scoped>
.tag {
  border: 1px solid #ccc
}
</style>