<template lang="html">
  <div class="">
    <countries-list :countries="countries"></countries-list>
  </div>
</template>

<script>
importing CountriesList from './components/CountriesList.vue';
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
  .then(countries => this.countries = contries)
  },
  components: {
    "countries-list": CountriesList
  }
}
</script>

<style lang="css" scoped>
</style>
