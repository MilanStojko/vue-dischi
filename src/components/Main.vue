<template>
  <div class="container">
    <Chosen :dischi="DiskArray" @selezionato="filtra" />
    <Disk v-for="(disco, index) in generiFiltrati" :key="index" :info="disco" />
  </div>
</template>

<script>
import axios from "axios";
import Disk from "./Disk.vue";
import Chosen from "./Chosen.vue";

export default {
  name: "Main",
  components: {
    Disk,
    Chosen,
  },
  data() {
    return {
      apiUrl: " https://flynn.boolean.careers/exercises/api/array/music",
      DiskArray: [],
      valoreGenere: "",
    };
  },
  created() {
    this.getData();
  },
  methods: {
    filtra(selected) {
      this.valoreGenere = selected;
    },
    filteredGenre() {
      this.DiskArray;
    },
    getData() {
      axios
        .get(this.apiUrl)
        .then((risposta) => {
          this.DiskArray = risposta.data.response;
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
  computed: {
    generiFiltrati() {
      return this.DiskArray.filter((genere) => {
        console.log(this.valoreGenere);
        return genere.genre.includes(this.valoreGenere);
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/variables.scss";
</style>