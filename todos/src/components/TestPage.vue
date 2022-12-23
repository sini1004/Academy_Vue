<template>
  <div> 
    <h4>{{text}}</h4>
  </div>
</template>

<script>
export default {
  name: 'Test',
  props: {
    text: String
  }
}
</script>

<style>
div h4 {
  font-size: 100px;
  font-weight: bold;
  color: #3FB883;
}
</style>