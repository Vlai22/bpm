<template>
  <div @click="OPWork()"  class="Worker">
    <img style="margin: 5px;" width="140" height="120 " src="@/assets/img/photo.jpg" alt="Photo">
    <div class="text">
      <h6>Name:{{worker.name}}</h6>
      <h6>Job title:{{worker.j_title}}</h6>
    </div>
  </div>
</template>

<script>
export default {
  name: "TableWorkers",
  methods: {
    OPWork(){
         this.$emit('open_card_worker',this.worker.uid);
    },
  },
  props:['worker'],
  data () {
    return{
    }
  }
}
</script>

<style scoped>
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
</style>