<template>
  <div class="open_cal"  @click="open">
  </div>
      <div id="cal"  class="calculator">
        <div class="history"></div>
        <div id="test" class="input" ><span>{{action}}</span></div>
        <div>
          <cal-btn @click="buttoncal('+')">+</cal-btn>
          <cal-btn @click="buttoncal('-')">-</cal-btn>
          <cal-btn @click="buttoncal('*')">*</cal-btn>
          <cal-btn @click="buttoncal('/')">/</cal-btn>
          <cal-btn @click="buttoncal('%')">%</cal-btn>
          <cal-btn @click="buttoncal('^')">^</cal-btn>
          <cal-btn @click="buttoncal('1')">1</cal-btn>
          <cal-btn @click="buttoncal('2')">2</cal-btn>
          <cal-btn @click="buttoncal('3')">3</cal-btn>
          <cal-btn @click="buttoncal('4')">4</cal-btn>
          <cal-btn @click="buttoncal('5')">5</cal-btn>
          <cal-btn @click="buttoncal('6')">6</cal-btn>
          <cal-btn @click="buttoncal('7')">7</cal-btn>
          <cal-btn @click="buttoncal('8')">8</cal-btn>
          <cal-btn @click="buttoncal('9')">9</cal-btn>
          <cal-btn @click="buttoncal('0')">0</cal-btn>
          <cal-btn @click="buttoncal('=')">=</cal-btn>
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
      console.log(e)
      if(this.key >= 0 && this.key <= 9){
          this.action += Number(this.key);
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
          this.sing = "%";
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
      this.action = String(this.action).trim();
    },
    calculate(){
        String(this.action).slice(`\n`).trim();
        this.values = String(this.action).split(String(this.sing));
        console.log(this.values);
        this.action = "";
        switch (this.sing){
          case "+":this.action = Number(this.values[0]) + Number(this.values[1]);
            this.sing = "";
          break;
          case "-": this.action = Number(this.values[0]) - Number(this.values[1]);
            this.sing = "";
          break;
          case "*": this.action = Number(this.values[0]) * Number(this.values[1]);
            this.sing = "";
          break;
          case "/": this.action = Number(this.values[0]) / Number(this.values[1]);
            this.sing = "";
          break;
          case "%": this.action = Number(this.values[0]) * Number(this.values[1]) / 100;
            this.sing = "";
          break;
          case "^": this.action = Math.pow(Number(this.values[0]), Number(this.values[1]));
            this.sing = "";
            break;
        }
    },
    buttoncal(s){
      this.input({key:s});
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
  width: 20px;
  height: 40px;
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