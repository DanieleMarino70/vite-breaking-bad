<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      selected: "",
    }
  },

  emits: ["option"],
  // components: {
  //   MyComponent,
  // },


};
</script>
<!-- v-model="selected" -->
<template>
  <select name="" id="" class="mt-5 mb-5" v-model="selected" @click="$emit('option', selected)">
        <option value="">Scegli tipo di carta</option>
        <option value="Spell Card">Spell Card</option>
    </select>
</template>

<style lang="scss" scoped>

</style>