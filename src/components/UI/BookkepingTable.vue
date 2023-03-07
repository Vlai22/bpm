<template>
      <div>
        <table id="table" class="table" border="1" width="1000" heigth="100">
            <thead>
              <th>///</th>
              <th v-for="arr_EN in arr_ENs" :key="arr_EN">{{arr_EN}}</th>
            </thead>
            <tbody>
              <tr  v-for="n in this.a" :key="n">
                <td>{{n}}</td>
                <td v-for="arr_EN in arr_ENs" :key="arr_EN" id="a" @click="test($event.target)" ></td>
              </tr>
            </tbody>
        </table>
      </div>
</template>

<script>
export default {
  name: "BookkepingTable",
  methods:{
    test(el){
      console.log(el);
    }
  },
  data(){
    return{
      a: 10,
      arr_ENs: ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'],
    }
  },
  mounted() {
    let  el = document.getElementById('table');
    let n = 0;
    let m = '1';
    for ( let i of el.rows){
      n=0;
      for( let j of i.cells){
          j.setAttribute( 'id',String(this.arr_ENs[n] + m));
          n++;
      }
      m++;
    }
  }
}
</script>

<style scoped>
.table{
}
</style>