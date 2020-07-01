<template>
    <div>
        <h3>{{msgLook[1].quoteAuthor}}</h3>
        <ul>
            <li v-for="look in msgLook" :key="look._id">{{look.quoteText}}</li>
        </ul>
    </div>
</template>
<script>
export default {
    name: "Quote",
  props:{
      msgLook: Array,
  },
}
</script>
<style scoped>
h3{
    text-align: left;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: 36px;
    line-height: 42px;
    margin: 5% 200px 0px 200px;
    padding-left: 10%;
}
li{
    border-left: 8px solid #F7DF94;
    margin: 5% 200px 0px 200px;
    list-style-type:none;
    font-family: Raleway;
    font-weight: 500;
    font-size: 36px;
    font-style: normal;
    padding-left: 5%;
}
@media screen and (max-width: 15cm){
    li{margin: 20% 200px 0px 0px;
    width: 100%;}
}
</style>