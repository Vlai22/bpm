<template>
       <div class="head">
         <div class="logo">
           <img src="" alt="#">
         </div>
         <div class="MainText">
           <p>About</p>
           <p>Feedback</p>
           <p>Options<select></select></p>
           <p>Profile</p>
         </div>
       </div>
</template>

<script>
export default {
  name: "HeadDefault",
}
</script>

<style scoped>
.head{
  display: flex;
  min-width: 100%;
  background-color: rgb(181, 196, 179);
  align-items: center;
  justify-content: space-between;
  align-content: space-between;
}
.MainText{
  display: flex;
  margin-right: 30px;
  align-items: end;
}
.logo{
  align-items: start;
  margin-left: 30px;
}
p{
  margin-left: 30px;
}
</style>