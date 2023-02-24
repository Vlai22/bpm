<template>
<div class="page">
  <component :is="title" @open_worker="open()" @exit_card_worker="exit()"></component>
</div>

</template>

<script>
import CardWorker from "@/components/UI/CardWorker";
import TableWorkers from "@/components/UI/TableWorkers";
export default {
  name: "WorkersMain",
  components: {
    CardWorker,
    TableWorkers,
  },
  data () {
    return{
      title: "TableWorkers",
    }
  },
  methods:{
    open(){
      this.title = "CardWorker";
    },
    exit(){
      this.title = "TableWorkers";
    },
  }
}
</script>

<style scoped>
.page{
  width: 100%;
  background-color: rgba(150,150,150,0.2);
}
</style>