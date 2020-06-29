<template>
  <div class='nala-toolbar'>
    <button v-on:click="runNala">Run Nala</button>
  </div>
</template>

<script>

import $ from 'jquery';
import axios from 'axios';

export default {
  name: 'NalaToolbar',
  props: {
    code: String,
    lineNumbers: Boolean
  },
  methods: {
      runNala() 
      {
          var codeEditor = $(".prism-editor-wrapper").first().find("pre").first();
          var nalaCode = codeEditor.text();
          axios.post("/api/nala", { content : nalaCode })
            .then((response) => 
            { 
                var result = response.data;

                var output = $("#nala-output");
                output.empty();
                output.append("Lexing Successful: " + result.lexingSuccessful + "<br>");
                output.append("Parsing Successful: " + result.parsingSuccessful + "<br>");
                output.append("Output:<br>");
                for (var i = 0; i < result.output.length; i++)
                {
                    output.append(result.output[i]);
                }

            });
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

button 
{
    margin-top:1em;
    padding:.85em;
    font-size:100%;
    background-color:#0066FF;
    color:white;
    border:0;
    border-radius:5px;
    cursor:pointer;
}

</style>