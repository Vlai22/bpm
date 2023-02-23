<template>
<button class="btn"><slot></slot></button>
</template>

<script>
export default {
  name: "BtnLeftBar"
}
</script>

<style scoped>
.btn{
  background-color: transparent;
  border: none;
  outline: none;
  font-size: 16px;
  width: 100%;
  height: 100px;
  border-bottom: 1px solid rgb(100,100,100);
}
.btn:hover{
  background-color: rgba(100,100,100,0.2);
}
</style>