<template>
  <div class="page">
    <div id="workers" class="Workers-row">
      <div class="Workers">
        <component :is="table" @open_card_worker="open" v-bind:worker="worker"  v-for="worker in workers" :key="worker.id"></component>
        </div>
      </div>
        <component :is="title" @exit_card_worker="exit" v-bind:uid="workeruid"></component>
    </div>
</template>

<script>
import TableWorkers from "@/components/UI/TableWorkers";
import CardWorker from "@/components/UI/CardWorker";
export default {
  name: "WorkersMain",
  components: {
    CardWorker,
    TableWorkers,
  },
  data () {
    return{
      title: "",
      table: "TableWorkers",
      workeruid: "",
      workers:[
        {id: 1,name: "Bob",j_title: "manager",uid:"123"},
        {id: 2,name: "Nick",j_title: "web-programmer",uid:"353"},
        {id: 3,name: "Kai",j_title: "software engineer",uid:"423"},
        {id: 4,name: "Tim",j_title: "manager",uid:"153"},
      ],
    }
  },
  methods: {
    open(a) {
      this.workeruid = a;
      this.table = "";
      this.title = "CardWorker";
    },
    exit(){
      this.title = "";
      this.table = "TableWorkers";
    }
  },
}
</script>

<style scoped>
.page{
  width: 100%;
  background-color: rgba(150,150,150,0.2);
}
.Workers-row{
  display: flex;
  flex-wrap: wrap;

}
.Workers{
  margin-left: 50px;
  margin-right: 50px;
  margin-top: 20px;
  display: flex;
}
</style>