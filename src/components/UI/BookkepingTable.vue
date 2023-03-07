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
                <td @click="test()" value="A1"> A 1 </td>
                <td @click="test()" value="B1"> A 2</td>
                <td @click="test()" value="C1"> A 3</td>
              </tr>
            </tbody>
        </table>
      </div>
</template>

<script>
export default {
  name: "BookkepingTable",
  methods:{
    test(e){
      console.log('ok' + e);
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