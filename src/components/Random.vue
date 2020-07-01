<template>
    <div class="change"> 
        <button class="change" @click="handleClick">random <i class="material-icons rec">autorenew</i></button>
    </div>
</template>
<script>
export default {
name: "Quote",

  methods: {
    handleClick() {
      this.$emit("change",true)
    },
  }
}
</script>
<style scoped>
.change{
    position: relative;
    right: -20%;
}
.change{
    position: relative;
    top: -10px;
    border:none;
    color: #333333;
    background: none;
    font-family: Raleway;
    font-style: normal;
    font-weight: 500;
    font-size: 18px;
    line-height: 120%;
}
.rec{
    position: relative;
    left: 16.67%;
    right: 16.67%;
    top: 3px;
    bottom: 10%;
    font-size: 20px;
}
.back{
    border: none;
    background: none;;
}
</style>