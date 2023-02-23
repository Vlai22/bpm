<template>
<div class="page">
  <div class="Workers-row">
    <div class="Workers">
      <div @click="OPWork()" class="Worker" v-for="worker in workers" :key="worker.id">
        <img style="margin: 5px;" width="140" height="120 " src="" alt="Photo">
        <div class="text">
          <h6>Name:{{worker.name}}</h6>
          <h6>Job title:{{worker.j_title}}</h6>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "WorkersMain",
  data () {
    return{
       workers:[
         {id: 1,name: "Bob",j_title: "manager",uid:"123"},
         {id: 2,name: "Nick",j_title: "web-programmer",uid:"353"},
         {id: 3,name: "Kai",j_title: "software engineer",uid:"423"},
         {id: 4,name: "Tim",j_title: "manager",uid:"153"},
       ]
    }
  },
  methods: {
    OPWork(){

    },
  }
}
</script>

<style scoped>
.page{
  width: 100%;
  background-color: rgba(150,150,150,0.2);
}
.Workers{
  margin-left: 50px;
  margin-right: 50px;
  margin-top: 20px;
  display: flex;
}
.Worker{
  margin: 10px;
  height: 200px;
  width: 150px;
  border: rgba(160,160,160,0.7) solid 1px;
}
.text {
  min-width: 140px;
  margin: 5px;
  height: 75px;
  /*border: black solid 1px;*/
}
h6{
  margin: 0px;
}
.Workers-row{
  display: flex;
  flex-wrap: wrap;

}
</style>