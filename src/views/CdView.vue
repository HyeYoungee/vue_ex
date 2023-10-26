<script>
import ButtonCounter from './ButtonCounter.vue';
import BlogPost from './BlogPost.vue';
import Home from './Tabs/home.vue';
import Post from './Tabs/post.vue';
import Archive from './Tabs/archive.vue';

export default {
  components: {
    ButtonCounter,
    BlogPost,
    Home,
    Post,
    Archive
  },
  data(){
    return{
      posts:[
        {id:1, title:'제목1'},
        {id:2, title:'제목2'},
        {id:3, title:'제목3'}
      ],
      postFontSize: 1,
      currentTab: 'Home',
      tabs: ['Home', 'Post', 'Archive']
    }
  }
}
</script>

<template>
  <div class="layout">
    <h1>This is an Components Basics page</h1>
    <ButtonCounter />  
    <ButtonCounter />  
    <ButtonCounter />  
    
    <hr>
    <h2>Blog</h2>
    <div :style="{ fontSize: postFontSize + 'em' }">
      <BlogPost
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        @enlarge-text="postFontSize += 0.1"
        @smaller-text="postFontSize -= 0.1"
      />

      <hr>
      <h2>Tab</h2>
      <div class="tabs">
        <div class="buttons">
          <button 
            v-for="tab in tabs"
            :key="tab"
            :class="['tab-button', {active: currentTab === tab}]"
            @click="currentTab = tab"
          >{{ tab }}</button>
          <component></component>
        </div>
      </div>
    </div>

  </div>
</template>

<style>
.buttons button{
  opacity: .6;
  padding: 10px;
}
.buttons button.active{
  opacity: 1;
}
</style>