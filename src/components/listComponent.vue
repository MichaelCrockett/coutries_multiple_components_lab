<template lang="html">
  <div class="">
    <li v-on:click='handleClick'>{{country.name}}</li>
  </div>
</template>

<script>
export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    handleClick() {
      eventBus.$emit('country-selected', this.country);
    }
  }
  components: {

  }
}
</script>

<style lang="css" scoped>
</style>
