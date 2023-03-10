<template >
  <HeadDefault></HeadDefault>
  <div style="display: flex">
  <LeftBar>
    <BtnLeftBar @click="open('WorkersMain')">Workers</BtnLeftBar>
    <BtnLeftBar @click="open('BookkeepingMain')">Bookkeeping</BtnLeftBar>
    <BtnLeftBar @click="open('WorkersMain')"></BtnLeftBar>
    <BtnLeftBar @click="open('WorkersMain')"></BtnLeftBar>
    <BtnLeftBar @click="open('WorkersMain')"></BtnLeftBar>
  </LeftBar>
  <component :is="page"></component>
  </div>
 <calculator-r></calculator-r>
  <footer-main></footer-main>
</template>

<script>
export default {
  data() {
    return {
      page: "WorkersMain"
    }
  },
  created() {
    history.pushState(null,null, "workers")
  },
  methods:{
    open(e){
      this.page = e;
      history.pushState(null,null, e.slice(0, e.length-4));
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
