<style>
.text{
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  color: black;
  font-size: 20px;
}
body{
  background-color: #999966;
}
</style>

<template>
  <div class="Calculator text">
    <h2>{{ msg }}</h2>
    {{n1bo ? n1 : null}} {{n2b ? n2 : null}} {{this.oper ? this.operator : " "}} {{n1b ? n1 : null}} <br><br>
    <button @click="getPlus" class="text">+</button><button @click="getMinus" class="text">-</button><button @click="getTimes" class="text">x</button><button @click="getDivision" class="text">/</button><br>
    <button @click="getDot" class="text">.</button><button @click="getResult" class="text">=</button><button @click="getAC" class="text">AC</button><br>
    <button @click="getSeven" class="text">7</button> <button @click="getEight" class="text">8</button> <button @click="getNine" class="text">9</button><br>
    <button @click="getFour" class="text">4</button><button @click="getFive" class="text">5</button><button @click="getSix" class="text">6</button><br>
    <button @click="getOne" class="text">1</button><button @click="getTwo" class="text">2</button><button @click="getThree" class="text">3</button><br>
    <button @click="getZero" class="text">0</button><br>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      msg: "Calculator",
      n1: "",
      n2: "",
      operator: "",
      oper: false,
      n1bo: true,
      n1b: false,
      n2b: false,
    };
  },
  methods:{
    getZero(){
      this.n1=this.n1 + "0";
    },
    getOne(){
      this.n1=this.n1 + "1";
    },
    getTwo(){
      this.n1=this.n1 + "2";
    },
    getThree(){
      this.n1=this.n1 + "3";
    },
    getFour(){
      this.n1=this.n1 + "4";
    },
    getFive(){
      this.n1=this.n1 + "5";
    },
     getSix(){
      this.n1=this.n1 + "6";
    },
     getSeven(){
      this.n1=this.n1 + "7";
    },
     getEight(){
      this.n1=this.n1 + "8";
    },
    getNine(){
      this.n1=this.n1 + "9";
    },
    getDot(){
      this.n1=this.n1 + ".";
    },
    getPlus(){
      this.operator="+";
      this.n2=this.n1;
      this.n1="";
      this.n1bo=false;
      this.n2b=true;
      this.oper=true;
      this.n1b=true;
    },
    getMinus(){
      this.operator="-";
      this.n2=this.n1;
      this.n1="";
      this.n1bo=false;
      this.n2b=true;
      this.oper=true;
      this.n1b=true;
    },
    getTimes(){
      this.operator="x";
      this.n2=this.n1;
      this.n1="";
      this.n1bo=false;
      this.n2b=true;
      this.oper=true;
      this.n1b=true;
    },
    getDivision(){
      this.operator="/";
      this.n2=this.n1;
      this.n1="";
      this.n1bo=false;
      this.n2b=true;
      this.oper=true;
      this.n1b=true;
    },
    getResult(){
      this.oper=false;
      this.n2b=false;
      if (this.operator==="+"){
        this.n1=this.n2*1.0+this.n1*1.0;
      }
      if (this.operator==="-"){
        this.n1=this.n2-this.n1;
      }
      if (this.operator==="x"){
        this.n1=this.n2*this.n1;
      }
      if (this.operator==="/"){
        this.n1=this.n2/this.n1;
      }
    },
    getAC(){
      this.n1="";
      this.n2="";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}*/
</style>
