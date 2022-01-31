<template>
  <div class="containerdisk">
    <img :src="info.poster" alt="" />
    <h3>{{ info.title }}</h3>
    <p>{{ info.author }}</p>
    <p>{{ info.year }}</p>
  </div>
</template>

<script>
export default {
  name: "Disk",
  props: {
    info: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/variables.scss";
.containerdisk {
  width: calc(1300px / 5);
  background-color: $mainColor;
  padding: 20px 20px 40px 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  img {
    width: 90%;
  }
  h3 {
    padding: 20px;
    text-align: center;
    font-weight: bold;
    text-transform: uppercase;
  }
  p{
    color: #60554d;
    padding: 3px;
  }
}
</style>