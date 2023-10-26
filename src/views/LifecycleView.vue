<script>
export default {
  mounted() {
    console.log(`컴포넌트 마운트 완료`)
  },
  beforeMount(){
    console.log(`컴포넌트 마운트 전`)
  },
  beforeUpdate(){
    console.log(`업데이트 시작`)
  },
  updated(){
    console.log(`업데이트 완료`)
  },
  data(){
    return{
      count: 0
    }
  }
}
</script>

<template>
  {{ console.log('템플릿 컴파일 시작') }}
  <div class="layout">
    <h1>This is an Lifecycle Hooks page</h1>
    <button @click="count++"> + </button>
    <div id="counter">{{ count }}</div>

  </div>
  {{ console.log('템플릿 컴파일 완료') }}

</template>

<style>

</style>