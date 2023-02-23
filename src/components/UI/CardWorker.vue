<template >
  <div>
       <div class="title">
         <img style="margin-right: 20px" width="300" height="350" src="@/assets/img/photo.jpg" alt="Photo">
         <div>
           <h2>Name:{{worker.name}}</h2>
           <h2>Job title: {{worker.j_title}}</h2>
           <h2>Status: {{worker.status}}</h2>
           <h2>Location: {{worker.location}}</h2>
         </div>
       </div>
      <div class="chat">
         <div class="input"></div>
      </div>
  </div>
</template>

<script>
export default {
  name: "CardWorker",
  data () {
    return {
      worker:{name:"Kolin",j_title:"programmer",status:"work",location:"Weisestraße 35, 12049 Berlin, Germany"},
    }
  }
}
</script>

<style scoped>
.title{
  display: flex;
  align-items: center;
  width: 70vw;
  margin-top: 10px;
  margin-right: auto;
  margin-left: auto;
}
.chat{
  border: black 1px solid;
  margin-right: auto;
  margin-left: auto;
  margin-top: 10px;
  align-items: center;
}
</style>