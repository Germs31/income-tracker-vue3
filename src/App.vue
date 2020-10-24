<template>
  <Header/>
</template>

<script>
import Header from '@/components/Header'
export default {
  setup(){
    return {
      Header
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira sans', sans-serif;
}

body {
  background: #eee;
}
</style>
