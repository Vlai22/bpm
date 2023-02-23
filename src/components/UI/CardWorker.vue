<template>
   <div class="title">
     <img style="margin-right: 20px" width="300" height="350" src="@/assets/img/photo.jpg" alt="Photo">
     <div>
       <h2>Name:{{worker.name}}</h2>
       <h2>Job title: {{worker.j_title}}</h2>
       <h2>Stutus: {{worker.stutus}}</h2>
       <h2>Job title: {{worker.j_title}}</h2>
       <h2>Job title: {{worker.j_title}}</h2>
     </div>
   </div>
</template>

<script>
export default {
  name: "CardWorker",
  data () {
    return {
      worker:{name:"Kolin",j_title:"programmer",stutus:"work"},
    }
  }
}
</script>

<style scoped>
.title{
  display: flex;
  align-items: center;
  margin-left:  25vw;
  margin-top: 10px;
}
</style>