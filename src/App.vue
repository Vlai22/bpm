<template >
  <HeadDefault></HeadDefault>
  <div style="display: flex">
  <LeftBar>
    <BtnLeftBar>Workers</BtnLeftBar>
    <BtnLeftBar>Bookkeeping</BtnLeftBar>
    <BtnLeftBar></BtnLeftBar>
    <BtnLeftBar></BtnLeftBar>
    <BtnLeftBar></BtnLeftBar>
  </LeftBar>
  <WorkersMain></WorkersMain>
  </div>
 <calculator-r></calculator-r>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style>
#app {
}
body{
  margin: 0;
}
</style>
