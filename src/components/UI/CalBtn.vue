<template>
   <button class="btn"><slot></slot></button>
</template>

<script>
export default {
  name: "CalBtn"
}
</script>

<style scoped>
.btn{
  border: none;
  outline: none;
  background-color: rgb(150,150,150);
  width: 30px;
  height: 30px;
  margin: 5px;
}
</style>