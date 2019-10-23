<template lang="html">
  <div>
    <select> //could add v-on:change="handleChange"
      <option v-for="(country, index) in countries" :key="index">{{country.name}}</option>
    </select>
  </div>

</template>

<script>
export default {
  name: 'country-select',
  props: ['countries'],
  // methods: {
  //   handleChange() {
  //     console.log("Im in the handlechange");
  //   }
  // }
}

</script>

<style lang="css" scoped>
</style>
