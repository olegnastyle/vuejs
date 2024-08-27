<template>
  <Header />
  <Counter />
  <Counter />
  <Counter />
  <Header />
</template>


<script setup>
  import { onMounted, ref } from 'vue'
  import Header from './components/Header.vue'
  import Counter from './components/Counter.vue'

  const counter = ref(0)
  const message = ref('')
  const checked = ref('true')
  
  // function increment () {
  //   counter.value++
  // }

  // хуки жизненного цикла
  onMounted(() => {
    console.log(counter)
  })
</script>

<style>
#app {
  width: 900px;
  margin: auto;
}
</style>