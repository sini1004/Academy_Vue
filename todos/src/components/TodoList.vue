<template>
  <div>
    <ul>
      <li class="shadow"></li>
      <li>할일</li>
      <li>할일</li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
    // Storage 내용을 넣을 빈 배열 생성
    todoItems:[]
    }
  },
  created: function(){
    if(localStorage.length>0){
      for(let i = 0; i < localStorage.length; i++){
        this.todoItems.push(localStorage.key(i));
      }
    }
  }
}
</script>

<style>

</style>