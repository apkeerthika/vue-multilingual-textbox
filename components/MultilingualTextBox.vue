<template lang="pug">
.text-box
  span.input(v-for="v, lang in value", :key="lang")
    input(type="text", :name="lang", :value="v", @input="update")
    span {{ lang }}
</template>

<script>
export default {
  props: {
    value: {
      type: Object,
      default: () => {
        return {}
      }
    }
  },
  methods: {
    update(e) {
      const { name, value } = e.target
      const newValue = { ...this.value, [name]: value }
      this.$emit('change', newValue)
    }
  }
}
</script>

<style lang="sass" scoped>
.text-box
  margin: 1rem 2rem
  .input
    display: flex
  input
    color: #000
    ::placholder
      color: #ccc
</style>
