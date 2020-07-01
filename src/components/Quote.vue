<template>
  <div class="looks">
    <p class="quote">{{ msg.quote }}</p>
    <div class="look" @click="handleLook">
      <i class="material-icons ok">arrow_right_alt</i>
      <p class="author">{{ msg.author }}</p>
      <p class="genre">{{ msg.quoteGenre }}</p>
    </div>

  </div>
</template>
<script>
export default {
  name: "Quote",
  props:{
      msg: Object,
  },
  methods: {
    handleLook(){
      this.$emit("handleLook",true)
    }
  }
};
</script>
<style scoped>

.looks{
    margin: 5% 200px 0px 200px;
    list-style-type:none;
    font-family: Raleway;
    font-weight: 500;
    font-size: 36px;
    font-style: normal;
}

.quote{
  border-left: 8px solid #F7DF94;
  padding-left: 5%;
  text-align: center;
  margin: 0;
  width: 672px;
  font-family: Raleway;
  font-weight: 500;
  font-size: 36px;
  font-style: normal;
}

.look{
   margin: 0;
   cursor: pointer;
   transition: ease-in 0.5s;
   text-align: center;
   justify-content: center;
   width: 672px;
   height: 151px;
   margin-left: 5%;
}
.ok{
  position: relative;
  float: right;
  color: white;
  top: 55px;
  left: 607;
  font-size:48px
}
.author{
  position: relative;
  top: 50px;
  left: 29px;
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
  font-size: 24px;
  line-height: 28px;
  color: #828282;
  text-align: left;
}
.genre{
  position: relative;
  top: 36px;
  left: 29px;
  font-family: Raleway;
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 16px;
  color: #828282;
  text-align: left;
}
.look:hover{
  background: #333333;
  color: white;

}
@media screen and (max-width: 15cm){
    .quote{
      margin: 0% 0px 0px 0px;
      padding: 0;
      width: 100%;
      }
    .look{
        margin: 0% 0px 0px 0px;
        padding: 0;
        width: 100%;
    }
    .looks{
      margin: 5% 0px 0px 0px;;
    }
    
}
@media screen and (max-width: 768px){
    .quote{
      margin: 0px 50px 0px 50px;
      padding: 0;
      width: 100%;
      }
    
}
</style>
