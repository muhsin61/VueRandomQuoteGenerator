<template>
  <div class="looks">
    <div class="myQuote"><p class="quote">{{ msg.quote }}</p></div>
    <div class="look" @click="handleLook">
      <div class="quoteInfo">
        <span class="material-icons ok">arrow_right_alt</span>
        <p class="author">{{ msg.author }}</p>
        <p class="genre">{{ msg.quoteGenre }}</p>
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
.look {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 100%;
  margin-top: 20px;
}
.quoteInfo{
  width: 672px;
  height: 151px;
  cursor: pointer;
  transition: ease-in 0.5s;
  position: relative;
  font-family: Raleway;
  font-style: normal;
}
.quoteInfo p{
  padding: 0;
  margin: 0;
  position: relative;
  top: 50px;
  left: 50px;
}
.author {
  font-weight: bold;
  font-size: 24px;
  line-height: 28px;
  color: #828282;
  text-align: left;
}
.genre {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 16px;
  color: #828282;
  text-align: left;
}
.ok {
  position: relative;
  top: 50px;
  float: right;
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
  }
}

</style>
