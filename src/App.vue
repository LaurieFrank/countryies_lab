<template lang="html">
  <div class="">
    <h1>Countries</h1>
    <country-select :countries="countries"></country-select>
    <country-detail :country="selectedCountry"></country-detail>
  </div>
</template>

<script>
import CountrySelect from './components/CountrySelect.vue';
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
  eventBus.$on('country-selected', (country) => {
    this.selectedCountry = country;
  });
  fetch('https://restcountries.eu/rest/v2/all')
  .then(res => res.json())
  .then(data => this.countries = data)
  },
  components: {
    "country-select": CountrySelect,
    "country-detail": CountryDetail
  }
}
</script>

<style lang="css" scoped>
</style>
