<template>
  <div class="container">
    <select @change="$emit('selezionato', selected)" v-model="selected">
      <option value="" selected>All</option>
      <option
        v-for="(genere, index) in genereArray"
        :key="index"
        :value="genere"
      >
        {{ genere }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Chosen",
  props: {
    dischi: Array,
  },
  data() {
    return {
      selected: "",
      genereArray: [],
    };
  },
  methods: {
    filtrageneri() {
      this.dischi.forEach((element) => {
        if (!this.genereArray.includes(element.genre)) {
          this.genereArray.push(element.genre);
        }
      });
    },
  },
  watch: {
    dischi: function () {
      this.filtrageneri();
    },
  },
};
</script>

<style>
</style>