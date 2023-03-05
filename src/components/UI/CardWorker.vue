<template >
  <div>
       <div class="title">
         <img style="margin-right: 20px" width="300" height="350" src="@/assets/img/photo.jpg" alt="Photo">
         <div>
           <h2>Name:{{workered.name}}</h2>
           <h2>Job title: {{workered.j_title}}</h2>
           <h2>Status: {{workered.status}}</h2>
           <h2>Location: {{workered.location}}</h2>
           <h2>UID: {{uid}}</h2>
         </div>
         <button @click="Exit()">Exit</button>
       </div>
      <div class="chat">
        <div class="message">
              <MessageWorkers v-bind:position="position">dasdas</MessageWorkers>
        </div>
         <div class="input">
           <img style="margin-top: 13px" width="30px" height="30px" src="@/assets/img/export.svg" alt="export">
           <textarea class="input_input" type="text"></textarea>
           <img style="margin-top: 3px" width="40px" height="50px" src="@/assets/img/send.svg" alt="send">
         </div>
      </div>
  </div>
</template>

<script>
import MessageWorkers from "@/components/UI/MessageWorkers";

export default {
  name: "CardWorker",
  components : {
    MessageWorkers,
  },
  data () {
    return {
      workered:{name:"Kolin",j_title:"programmer",status:"work",location:"Weisestraße 35, 12049 Berlin, Germany",id:"112"},
      position: "left",
    }
  },
  props:{uid: String},
  methods:{
    Exit(){
      this.$emit('exit_card_worker');
      window.history.pushState(null,null, "workers");
    }
  },
  mounted() {
    console.log(this.uid);
    window.history.pushState(null,null, "/" + this.uid)
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
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}
.message{
  width: 100%;
  height: 500px;
  border-bottom: 1px solid black;
}
.input_input{
  background-color: transparent;
  /*margin-bottom: 40px;*/
  margin-left: 20px;
  margin-top: 10px;
  width: 300px;
  border-radius: 20px;
  height: 30px;
}
</style>