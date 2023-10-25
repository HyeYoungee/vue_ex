<script>
export default{
  data(){
    return{
      awesome:false,
      type:'C',
      page:true
    }
  }
}
</script>

<template>
  <div class="layout">
    <h1>Conditional Rendering page</h1>
    <button @click="awesome = !awesome">전환</button>
    <h1 v-if="awesome">Vue는 정말 멋지죠!</h1>
    <h1 v-else>아닌가요? 😢</h1>
    <hr>

    <div v-if="type === 'A'">
      A
    </div>
    <div v-else-if="type === 'B'">
      B
    </div>
    <div v-else-if="type === 'C'">
      C
    </div>
    <div v-else>
      A/B/C 아님
    </div>

    <hr>
    <button @click="page =! page" :class="{ active: page }">페이지 전환</button>
    <!-- <template v-if="page === true"> -->
    <template v-if="page">
      <h1>제목1</h1>
      <p>단락 1</p>
      <p>단락 2</p>
      <div v-show="true">Hello!</div>
    </template>
    <!-- <template v-if="page === false"> -->
    <template v-else>
      <h1>제목2</h1>
      <p>단락 1</p>
      <p>단락 2</p>
      <div v-show="false">World!</div>
    </template>

  </div>
</template>

<style>
  button.active{
    background: #4ab189;
    color: #fff;
  }
</style>