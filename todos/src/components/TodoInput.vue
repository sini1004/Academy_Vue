<template>
  <div class="inputBox">
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
      if(this.newTodoItem !== ' '){
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
  .inputBox { 
    height: 50px;
    line-height: 50px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 30px;
  }
  input {
    width: calc(90% - 50px);
    border-radius: 30px;
    border: none;
    padding: 0 20px;
    font-size: 1rem;
  }
  input:focus {
    outline: none;
  }
  span {
    background: #6c1eb6;
    color: white;
    font-size: 1.2rem;
    width: 50px;
    border-radius: 50px;
  }
  i {
    vertical-align: middle;
    transition: .4s ease-in;
  }
  i:hover {
    transform: rotate(90deg);
  }
</style>