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
      window.addEventListener('keydown',this.input);

  },
  data () {
    return{j:0, i: "",sing: "",action : "",values:[],key: ""}
  },
  methods : {
    input(e) {
      this.key = e.key;
      if(this.key >= 0 && this.key <= 9){
          this.action += this.key;
      }else{
        switch (this.key){
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
          case "Backspace": this.action = this.action.slice(0,-1);
          break;
          case "Delete": this.action = "";
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
        document.getElementById("cal").style.display = "block";
      }else{
        document.getElementById("cal").style.display = "none";
        this.input({key:"Delete"});
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