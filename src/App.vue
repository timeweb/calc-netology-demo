<template>
  <div id="app">
    <calc-view msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import CalcView from './components/CalcView.vue'

export default {
  name: 'App',

  components: {
    CalcView
  }
}
</script>
