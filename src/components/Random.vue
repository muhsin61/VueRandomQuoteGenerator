<template>
  <div class="change">
    <div>
      <p @click="handleClick">random</p>
      <i class="material-icons rec">autorenew</i>
    </div>
  </div>
</template>
<script>
export default {
  name: "Quote",

  methods: {
    handleClick() {
      this.$emit("change", true);
    },
  },
};
</script>
<style scoped>
.change {
  position: relative;
  margin: 30px 30px 0 0;
  float: right;
}
.change div{
  position: relative;
  margin-left: auto;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.change p {
  font-weight: 700;
}
</style>
