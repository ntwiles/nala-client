<template>
  <div id="app">
    <h1>nala code editor</h1>
    <div class='nala-container'>
      <NalaEditor/>
      <NalaOutput/>
    </div>
    <NalaToolbar/>
  </div>
</template>

<script>

import NalaEditor from './components/NalaEditor.vue'
import NalaOutput from './components/NalaOutput.vue'
import NalaToolbar from './components/NalaToolbar.vue'

export default {
  name: 'App',
  components: {
    NalaEditor,
    NalaOutput,
    NalaToolbar
  }
}
</script>

<style>
#app 
{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.nala-container
{
  display:flex;
  justify-content: space-evenly;
}
</style>
