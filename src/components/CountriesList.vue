<template lang="html">
  <div class="">
    <select class="" name="country-select">
      <option v-for="(country, index) in countries">{{country.name}}</option>
    </select>
    <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul>
  </div>
</template>


<script>
import listComponent from './listComponent.vue';

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": listComponent
  }
}
</script>

<style lang="css" scoped>
</style>
