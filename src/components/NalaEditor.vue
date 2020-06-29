<template>
  <div class='nala-editor'>
  <prism-editor :code="code" language="nala"></prism-editor>
  </div>
</template>

<script>
import Prism from 'prismjs'
import PrismEditor from 'vue-prism-editor'
import "prismjs/components/prism-nala.js"
import "prismjs/themes/prism-tomorrow.css";

export default {
  name: 'NalaEditor',
  components: {
    PrismEditor,
    Prism    
  },
  data: function() {
      return {
          weathers : []
      }

  },
  props: {
    code: String,
    lineNumbers: Boolean
  },
  /*
  mounted() 
  {
      fetch("https://localhost:44375/weatherforecast")
        .then(response => response.json())
        .then((data) => {
            this.weathers = data;
            console.log(data);
        })
  }
  */
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

<!-- TODO: This is not scoped so I can apply it to prism-editor, there must be a better way! -->
<style>
.nala-editor
{
    width:50%;
}

.prism-editor-wrapper 
{
    width:100%;
    margin-left:auto;
    margin-right:auto;
}

.prism-editor-wrapper pre
{
    min-height:30em;
    margin:0;
}
</style>