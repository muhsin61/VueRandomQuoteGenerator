<template>
  <div>
    <h3>{{ quotes[1].quoteAuthor }}</h3>
    <div class="quotes">
      <ul>
        <li v-for="look in quotes" :key="look._id">{{ look.quoteText }}</li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: "Quote",
  props: {
    quotes: Array,
  },
};
</script>
<style scoped>
div{
    font-family: Raleway;
    font-style: normal;
}
.quotes{
    display: flex;
    justify-content: center;
}
h3 {
  position: relative;
  text-align: center;
  font-weight: bold;
  font-size: 36px;
  line-height: 42px;
}
ul{
    padding: 0;
    margin: 0;
}
li {
  border-left: 8px solid #f7df94;
  width: 672px;
  list-style-type: none;
  font-size: 36px;
  font-style: normal;
  padding: 0;
  margin: 0;
  margin-bottom: 20px;
}
@media screen and (max-width: 15cm) {
  li {
    width: 100%;
    left: 0;
    font-size: 25px;
  }
}
</style>
