<template>
  <div id="nala-output" class="nala-output"></div>
</template>

<script>
export default {
  name: 'NalaOutput',
  components: {
  },
  props: {
    code: String,
    lineNumbers: Boolean
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.nala-output 
{
    width:50%;
    background-color:#383838;
    color:#eee;
    padding:1em;
    text-align: left;
    font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace;
}
</style>