<template lang="html">
  <div class="">
    <li v-on:click='handleClick'>{{country.name}}</li>
  </div>
</template>

<script>
import {eventBus} from '../main.js';


export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    handleClick() {
      eventBus.$emit('country-selected', this.country);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
