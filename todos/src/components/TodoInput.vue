<template>
  <div class="">
    <input type="text" placeholder="Please enter a task to do." v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <span v-on:click="addTodo">
      <i class="fa-solid fa-plus"></i>
    </span>
  </div>
</template>

<script>
export default {
  data(){
    return {
      newTodoItem:''
    }
  },
  methods: {
    addTodo(){
      // localStorage.setItem(this.newTodoItem, this.newTodoItem);
      // console.log('클릭', this.newTodoItem);
      if(this.newTodoItem !== ''){
        let value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(value,value);
        this.clearInput(); // 분리 단일 책임 원칙
      }
    },
    clearInput(){
      // 인풋박스 입력 후 초기화
      this.newTodoItem = '';
    }
  }
}
</script>

<style scoped>
  
</style>