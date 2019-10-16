<template lang="html">
  <div class="">
    <h1>Countries</h1>
    <countries-list :countries='countries'></countries-list>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import {eventBus} from './main.js'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
      .then(res => res.json())
      .then(data => this.countries = data);

      eventBus.$on('country-selected', (country) => {
        this.selectedCountry = country;
      });

  },
  components: {
    'countries-list': CountriesList,
  }


}
</script>

<style lang="css" scoped>
</style>
