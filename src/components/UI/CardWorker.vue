<template >
  <div>
       <div class="title">
         <img style="margin-right: 20px" width="300" height="350" src="@/assets/img/photo.jpg" alt="Photo">
         <div>
           <h2>Name:{{workered.name}}</h2>
           <h2>Job title: {{workered.j_title}}</h2>
           <h2>Status: {{workered.status}}</h2>
           <h2>Location: {{workered.location}}</h2>
           <h2>ID: {{id}}</h2>
         </div>
         <button @click="Exit()">Exit</button>
       </div>
      <div class="chat">
         <div class="input">
           <input type="text">
         </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "CardWorker",
  data () {
    return {
      workered:{name:"Kolin",j_title:"programmer",status:"work",location:"Weisestraße 35, 12049 Berlin, Germany"},
    }
  },
  methods:{
    Exit(){
      this.$emit('exit_card_worker');
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
  width: 70vw;
}
.input{
  width: 100%;
}
</style>