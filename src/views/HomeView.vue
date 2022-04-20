<template>
  <div>
    <VueMultiselect v-model="selected" :options="options" :close-on-select="true" :clear-on-select="false"
      placeholder="Select one" label="name" track-by="name">
    </VueMultiselect>
  </div>
</template>

<script>
import VueMultiselect from 'vue-multiselect'
export default {
  components: { VueMultiselect },
  data() {
    return {
      selected: null,
      options: ['list', 'of', 'options']
    }
  }
}
</script>

<style src="vue-multiselect/dist/vue-multiselect.css">
</style>