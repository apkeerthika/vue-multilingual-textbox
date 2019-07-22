<template lang="pug">
.page
  h1 Multilinugal Text Box
  multilingual-text-box(:value="value", @change="update")
</template>

<script>
import MultilingualTextBox from '~/components/MultilingualTextBox.vue'

export default {
  components: {
    MultilingualTextBox
  },
  data() {
    return {
      value: {
        en: 'Keerthi',
        ta: 'கீர்த்தி',
        ar: 'كيرثي'
      }
    }
  },
  methods: {
    update(value) {
      this.value = value
    }
  }
}
</script>

<style lang="sass" scoped>
.page
  h1
    margin: 1rem 3rem
</style>
