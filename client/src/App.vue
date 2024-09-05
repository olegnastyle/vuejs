<template>
  <homeHeader />
  <component :is="currentView" />
  <homeFooter />
</template>

<script setup>
  import { ref, computed } from 'vue'
  import homeHeader from './components/home-header.vue';
  import homeFooter from './components/home-footer.vue';
  import homeMain from './components/home-main.vue';
  import myBlog from './components/my-blog.vue';
  import homeAbout from './components/home-about.vue';
  import homeContact from './components/home-contact.vue';
  import homeError from './components/home-error.vue';

  const routes = {
    '/home': homeMain,
    '/about': homeAbout,
    '/blog': myBlog,
    '/contact': homeContact
  }

  const currentPath = ref(window.location.hash)

  window.addEventListener('hashchange', () => {
    currentPath.value = window.location.hash
  })

  const currentView = computed(() => {
    return routes[currentPath.value.slice(1) || '/'  || homeError]  
  })
</script>

<style scoped>

</style>