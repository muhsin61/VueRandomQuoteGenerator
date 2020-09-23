<template>
  <div class="looks">
    <div class="myQuote"><p class="quote">{{ msg.quote }}</p></div>
    <div class="look" @click="handleLook">
      <div class="quoteInfo">
        <div>
          <p class="author">{{ msg.author }}</p>
          <p class="genre">{{ msg.quoteGenre }}</p>
        </div>
        <span class="material-icons ok">arrow_right_alt</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Quote",
  props: {
    msg: Object,
  },
  methods: {
    handleLook() {
      this.$emit("handleLook", true);
    },
  },
};
</script>
<style scoped>
p{
  margin: 0;
  padding: 0;
}
.looks {
  display: block;
  text-align: left;
  list-style-type: none;
  font-family: Raleway;
  font-weight: 500;
  font-size: 36px;
  font-style: normal;
  width: 100%;
}
.myQuote{
  width: 100%;
  display: flex;
  justify-content: center;
}
.quote {
  border-left: 8px solid #f7df94;
  text-align: left;
  padding-left: 20px;
  margin: 0;
  width: 672px;
  font-family: Raleway;
  font-weight: 500;
  font-size: 36px;
  font-style: normal;
}
.genre{
  font-size: 15px;
}
.look {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 100%;
  margin-top: 20px;
}
.quoteInfo{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 672px;
  height: 151px;
  cursor: pointer;
  transition: ease-in 0.5s;
  font-family: Raleway;
}
.ok {
  color: white;
  font-size: 48px;
  width: 50px;
  height: 50px;
}
.quoteInfo:hover {
  background: #333333;
  color: white;
}
@media screen and (max-width: 15cm) {
  .quote {
    margin: 5px;
    padding: 5px;
    width: 100%;
    font-size: 25px;
  }
  .author{
    font-size: 25px;
  }
}

</style>
