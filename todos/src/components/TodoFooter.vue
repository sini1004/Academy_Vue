<template>
  <div>
    <span @click="clearTodo">Clear All</span>
  </div>
</template>

<script>
export default {
  methods:{
    clearTodo(){
      // localStorage에서만 삭제
      localStorage.clear();
    }
  }
}
</script>

<style>

</style>