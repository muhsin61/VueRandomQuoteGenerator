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
  display: flex;
  justify-content: flex-end;
  text-align: center;
  align-items: center;
  padding-right: 30px;
  
}
.change div{
  cursor: pointer;
}
.change p {
  position: relative;
  padding: 0;
  margin: 0;
  display: inline-block;
  color: #333333;
  background: none;
  font-family: Raleway;
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 120%;
}
.rec {
  position: relative;
  top: 5px;
  font-size: 20px;
  transition: 1s;
}
</style>
