<template>
  <div class="open_cal"  @click="open">
  </div>
      <div id="cal"  class="calculator">
        <div class="history"></div>
        <div id="test" class="input" ><span>{{action}}</span></div>
        <div>
          <cal-btn>+</cal-btn>
        </div>
      </div>

</template>

<script>
export default {
  name: "CalculatorR",
  created() {
      window.addEventListener('keypress',this.input);

  },
  data () {
    return{j:0, i: "",sing: "",action : "",values:[]}
  },
  methods : {
    input(e) {
      console.log(e.key);
      if(e.key >= 0 && e.key <= 9){
          this.action += e.key;
      }else{
        switch (e.key){
          case "+": this.action += "+";
          this.sing = "+";
          break;
          case "-": this.action += "-";
          this.sing = "-";
          break;
          case "*": this.action += "*";
          this.sing = "*";
          break;
          case "/": this.action += "/";
          this.sing = "/";
          break;
          case "%": this.action += "%";
          this.sing = "^";
          break;
          case "^": this.action +=  "^";
          this.sing = "^";
          break;
          case "Enter": this.calculate();
          break;
          case "=": this.calculate();
          break;
        }
      }
    },
    calculate(){
        this.values = this.action.split(this.sing);
        switch (this.sing){
          case "+": this.action =  Number(this.values[0]) + Number(this.values[1]);
          break;
          case "-": this.action =  Number(this.values[0]) - Number(this.values[1]);
          break;
          case "*": this.action =  Number(this.values[0]) * Number(this.values[1]);
          break;
          case "/": this.action =  Number(this.values[0]) / Number(this.values[1]);
          break;
          case "%": this.action =  Number(this.values[0]) * Number(this.values[1]) / 100;
          break;
        }
    },
    open(){
      if(window.getComputedStyle(document.getElementById("cal")).display == "none"){
        console.log("ok");
        document.getElementById("cal").style.display = "block";
      }else{
        document.getElementById("cal").style.display = "none";
      }
    }
  }
}
</script>

<style scoped>
.open_cal{
  position: fixed;
  background-color: rgba(1,1,1,0.2);
  width: 50px;
  height: 100px;
  right: 0px;
  top: 50px;
  z-index: 2;
}
.history{
  width: 100%;
  height: 20px;
  background-color: rgba(100,100,100,0.1);
}
.calculator{
  position: fixed;
  background-color: rgba(1,1,1,0.2);
  width: 300px;
  height: 400px;
  right: 0px;
  top: 50px;
  z-index: 1;
  display: none;
}
.input{
  width: 100%;
  height: 40px;
  background-color: rgba(150,150,150,0.1);
}
</style>