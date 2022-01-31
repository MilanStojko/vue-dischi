<template>
  <header>
    <img src="../assets/img/Spotify_logo_without_text.svg" alt="" />
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
@import "../assets/style/variables.scss";
header {
  background-color: $mainColor;
  img {
    height: 80px;
    margin: 10px;
  }
}
</style>