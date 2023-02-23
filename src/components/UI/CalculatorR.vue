<template>
  <div class="open_cal"  >
      <div onclick="click()" class="calculator">
        <div class="history"></div>
        <div id="test" class="input" ><span>Value: {{a}}</span></div>
        <div>
          <cal-btn>+</cal-btn>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "CalculatorR",
  data () {
    return{a : ''}
  },
  methods : {
    click () {
      document.addEventListener('keydown', function (e){
        console.log(e.key);
      this.test(e.key);
      });

    },
    test : function test(e) {
      this.a = e;
      console.log(e);
      document.addEventListener("keydown", );
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
}
.input{
  width: 100%;
  height: 40px;
  background-color: rgba(150,150,150,0.1);
}
</style>