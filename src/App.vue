<template lang="html">
  <div class="">
    <h1>Countries</h1>
    <div class="main-container">
      <countries-list :countries='countries'></countries-list>
      <country-detail v-if='selectedCountry' :country='selectedCountry'></country-detail>
    </div>
  </div>


</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
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
    'country-detail': CountryDetail
  }


}
</script>

<style lang="css" scoped>

.main-container {
  display: flex;
  justify-content: space-between;
}

</style>
