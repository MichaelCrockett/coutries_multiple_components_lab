<template lang="html">
  <div class="">
    <h2>{{ country.name }}</h2>
    <h3>Capital city: {{ country.capital }}</h3>
    <h3>Population: {{ country.population}}</h3>

  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
