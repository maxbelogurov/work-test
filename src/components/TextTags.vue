<template>
  <v-row :justify="Align" class="tags-container px-3">
    <v-col v-for="(tag, i) in Tags"
           :key="i"
           :class="Align === 'start' ? 'col-auto' : ''"
           class="tags-container__item ps-0 pe-2 py-0">
      <v-icon v-if="i !== 0">mdi-circle-small</v-icon>
      <div class="tags-container__item__body">
        <v-icon>{{ tag.icon }}</v-icon>
        <div>{{ tag.text }}</div>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "TextTags",
  props: ['Tags', 'Align']
}
</script>

<style scoped>

</style>
