<script>
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      },
      firstName: 'John',
      lastName: 'Doe'
    }
  },
  computed: {
    // 계산된 값을 반환하는 속성
    publishedBooksMessage() {
      // `this`는 컴포넌트 인스턴스를 가리킵니다.
      return this.author.books.length > 0 ? 'Yes' : 'No'
    },
    fullName: {
      get(){
        return this.firstName + ' ' + this.lastName
      },
      set(newValue){
        [this.firstName, this.lastName] = newValue.split(' ');
      }
    }
  }
}
</script>

<template>
  <p>책을 가지고 있다:</p>
  <span>{{ publishedBooksMessage }}</span>
  <hr>

  <div>Name: {{ this.fullName }}</div><!-- get() -->
  <div>이름: {{ this.fullName="길동 홍" }}</div><!-- set() -->
</template>





<!-- <script setup>
  import { reactive } from 'vue'

  const author = reactive({
    name: 'John Doe',
    books: [
      'Vue 2 - Advanced Guide',
      'Vue 3 - Basic Guide',
      'Vue 4 - The Mystery'
    ]
  })
</script>

<template>  
  <div class="layout">
    <h1>Properties page</h1>

    <p>Has published books:</p>
    <span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span>

  </div>

</template>

<style>
@media (min-width: 1024px) {
  .layout {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style> -->
