<template>
<div class="LeftBar">
   <slot></slot>
</div>
</template>

<script>
export default {
  name: "LeftBar"
}
</script>

<style scoped>
.LeftBar{
  position: relative;
  background-color: rgb(122, 222, 95);
  width: 100px;
  height: 100vh;
}
</style>