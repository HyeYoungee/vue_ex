<script>
export default {
  data() {
    return {
      list: [
        'html','css', 'javascript'
      ]
    }
  },
  mounted() {
    this.$refs.input.focus()
    // document.querySelector('#username').focus()
    console.log(this.$refs.items)
  }
}
</script>

<template>

  <div class="layout">
    <h1>This is an Refs page</h1>
    <input ref="input">
    <!-- <input type="text" id="username"> -->

    <hr>
    <ul>
      <li v-for="item in list" ref="items" :key="item.id">
        {{ item }}
      </li>
    </ul>   

  </div>
</template>

<style>
</style>