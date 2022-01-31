<template>
  <div class="container">
    <Disk v-for="(disco, index) in DiskArray" :key="index" :info="disco" />
  </div>
</template>

<script>
import axios from "axios";
import Disk from "./Disk.vue";

export default {
  name: "Main",
  components: {
    Disk,
  },
  data() {
    return {
      apiUrl: " https://flynn.boolean.careers/exercises/api/array/music",
      DiskArray: [],
    };
  },
  created() {
    this.getData();
  },
  methods: {
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
};
</script>

<style lang="scss" scoped>
@import "../assets/style/variables.scss";
</style>