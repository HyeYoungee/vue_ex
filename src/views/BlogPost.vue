<script>
export default{
  props: ['title'],
  emits: ['enlarge-text','smaller-text']
}
</script>

<template>
  <h3>{{ title }}</h3>
  <!-- <button>텍스트 확대</button> -->
  <button @click="$emit('enlarge-text')">텍스트 확대</button>
  <button @click="$emit('smaller-text')">텍스트 축소</button>
</template>  