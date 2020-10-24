<template>
  <Header :totalIncome="state.totalIncome"/>
</template>

<script>
import { reactive, computed } from 'vue'
import Header from '@/components/Header'
export default {
  setup(){
    const state = reactive({
      income: [{
        value: 400
      }],
      totalIncome: computed(() => {
        let temp = 0;
        if(state.income.length > 0){
          for(let i = 0; i <state.income.length; i++){
            temp += state.income[i].value
          }
        }

        return temp
      })
    })
    return {
      Header,
      state
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
