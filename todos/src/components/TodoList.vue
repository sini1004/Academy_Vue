<template>
  <div>
    <ul>
      <li class="shadow" v-for="(todoItem, index) in todoItems" :key="index">
        <span><i class="checkBtn fa-solid fa-check"></i></span>
        <span class="todolist">{{ todoItem }}</span>
        <span class="removeBtn" @click="removeTodo(todoItem, index)"><i class="fa-solid fa-trash"></i></span>
      </li>
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
  },
  methods: {
    removeTodo(todoItem, index){
      localStorage.removeItem(todoItem)
      this.todoItems.splice(index, 1);
      // console.log('키 : ' + index + ' 밸류 : ' + todoItem)
    }
  }
}
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
}
ul li {
  display: flex;
  height: 50px;
  line-height: 50px;
  background: white;
  margin: 1rem 0;
  border-radius: 30px;
  padding: 0 20px;
  text-align: left;
}
.checkBtn {
  margin-right: 10px;
  color: blueviolet;
}
.todolist {
  white-space: normal;
  overflow: hidden;
  text-overflow: ellipsis;
}
.removeBtn {
  margin-left: auto;
}
.removeBtn i {
  transition: .4s ease-in;
}
.removeBtn i:hover {
  transform: scale(1.2);
}
</style>