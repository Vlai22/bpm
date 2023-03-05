<template>
    <div :class="position"><slot></slot></div>
</template>

<script>
export default {
  name: "MessageWorkers",
  props :{ position : String},
  data () {
    return {
      uid: "",
    }
  },
}
</script>

<style scoped>
.message{
  display: inline-block;
  position: relative;
  width: auto;
  height: auto;
  margin-top: 10px;
  margin-bottom: 10px;
  padding: 5px;
  border-radius: 20px;
  border: 1px solid rgb(0, 120, 110);
  color: rgb(5, 26, 24);
  background-color: rgba(0, 120, 110, 0.2);
}
.rigth{
  float: right;
  right: 20px;
  display: inline-block;
  position: relative;
  width: auto;
  height: auto;
  margin-top: 10px;
  margin-bottom: 10px;
  padding: 5px;
  border-radius: 20px;
  border: 1px solid rgb(0, 120, 110);
  color: rgb(5, 26, 24);
  background-color: rgba(0, 120, 110, 0.2);
}
.left{
  float: left;
  left: 20px;
  display: inline-block;
  position: relative;
  width: auto;
  height: auto;
  margin-top: 10px;
  margin-bottom: 10px;
  padding: 5px;
  border-radius: 20px;
  border: 1px solid rgb(0, 120, 110);
  color: rgb(5, 26, 24);
  background-color: rgba(0, 120, 110, 0.2);
}
</style>