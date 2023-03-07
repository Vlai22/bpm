<template>
      <div>
        <table class="table">
            <thead>
              <th>test 1 </th>
              <th>test 2 </th>
              <th>test 3 </th>
            </thead>
            <tbody>
              <tr>
                <td @click="test1($event.target)" test="lol" id="A1"> A 1 </td>
                <td @click="test1($event.target)" id="B1"> A 2</td>
                <td @click="test1($event.target)" id="C1">A 3</td>
              </tr>
            </tbody>
        </table>
      </div>
</template>

<script>
export default {
  name: "BookkepingTable",
  methods:{
    test1(el){
      console.log(el.getAttribute('id'));
    }
  }
}
</script>

<style scoped>
.table{
  border: 1px solid black;
  border-radius: 1px;
}
</style>