<script setup>
import BlogPost from './components/BlogPost.vue';
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';

const posts = ref([
  {id:1, title: 'My journey with Vue'},
  {id:2, title: 'Blogging with Vue'},
  {id:3, title: 'Why vue is so fun'}
])
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <!-- <TheWelcome /> -->
    <BlogPost
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
    />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
