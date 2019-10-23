<template lang="html">
  <div v-if='country'>
    <h3>{{ country.name }}</h3>
    <p>population: {{ country.population }}</p>
    <p>capital: {{ country.capital }}</p>
  </div>
</template>

<script>
export default {
  name: "country-detail",
  props: ["country"]
}
</script>

<style lang="css" scoped>
</style>
