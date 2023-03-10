<template>
  <div style="overflow: auto; width: 100vh; margin-left: 40px; height: 100vh">
    <table id="table" class="table">
      <thead>
      <th>///</th>
      <th v-for="arr_EN in arr_ENs" :key="arr_EN">{{ arr_EN }}</th>
      </thead>
      <tbody>
      <tr v-for="n in this.a" :key="n">
        <td id="b">{{ n }}</td>
        <td v-for="arr_EN in arr_ENs" :key="arr_EN" id="a"
            @click="click_cell($event.target)"></td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "BookkepingTable",
  methods: {
    click_cell(el) {
      if(window.getComputedStyle(el).border == "0.8px solid rgb(221, 221, 221)"){
        el.style.border = "3px solid green";
        document.getElementById(this.element).style.border = "1px solid #dddddd";
        this.element = el.getAttribute('id');
        if(window.getComputedStyle(el).border == "0.8px solid rgb(221, 221, 221)"){
          this.press = false;
        }else {
          this.press = true;
        }
      }else{
        el.style.border = "1px solid #dddddd";
      }
    },
    input (e) {
      console.log(e.key);
      console.log(this.element)
        if(this.press == true){
          let a = document.getElementById(this.element).innerHTML;
          if(e.key == "Backspace"){
             document.getElementById(this.element).innerHTML = a.substring(0,a.length - 1);
          }else if( e.key == "Enter"){
              document.getElementById(this.element).innerHTML += "\n";
          }else if(e.key == "Control"){
            document.getElementById(this.element).innerHTML += "";
          }else if(e.key == "ArrowLeft"){
            for(let i = 0; i < this.arr_ENs.length-1;i++){
              if(this.arr_ENs[i] == this.element.substring(0,this.element.length - 1)){
                document.getElementById(this.arr_ENs[i - 1] + this.element.substring(1)).style.border = "3px solid green";
                document.getElementById(this.element).style.border = "1px solid #dddddd";
                 this.element = this.arr_ENs[i - 1] + this.element.substring(1);
              }
            }
          }else if(e.key == "ArrowRight"){
            for(let i = 0; i < this.arr_ENs.length-1;i++){
              if(this.arr_ENs[i] == this.element.substring(0,this.element.length - 1)){
                console.log("ok");
                document.getElementById(this.arr_ENs[i + 1] + this.element.substring(1)).style.border = "3px solid green";
                document.getElementById(this.element).style.border = "1px solid #dddddd";
                this.element = this.arr_ENs[i + 1] + this.element.substring(1);
              }
            }
          }
          else {
                document.getElementById(this.element).innerHTML += e.key;
          }
        }
    },
  },
  data() {
    return {
      a: 10,
      element: "1",
      press: false,
      arr_ENs: ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'],
    }
  },
  mounted() {
    let el = document.getElementById('table');
    let n = 0;
    let m = '1';
    for (let i  of el.rows ) {
      n = 0;
      for (let j of i.cells ) {
        if(j.getAttribute("id") == "b"){
           j.setAttribute("id", String(m));
        }else {
          j.setAttribute('id', String(this.arr_ENs[n - 1] + m));
        }
        n++;
      }
      m++;
    }
   window.addEventListener("keydown", this.input,false);
  }
}
</script>

<style scoped>
.table {
  width: 100%;
  margin-bottom: 20px;
  border: 1px solid #dddddd;
  border-collapse: collapse;
}
.table th {
  font-weight: bold;
  padding: 5px;
  background: #efefef;
  border: 1px solid #dddddd;
}
.table td {
  border: 1px solid #dddddd;
  padding: 5px;
}
.table td:hover{
  background-color: rgba(150,150,150,0.2);
}
</style>