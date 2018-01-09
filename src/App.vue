<template>
  <div id="app">
    <h1 class="text-center">Word Translator</h1>
    <h4 class="text-center">Powered By Vue.js</h4>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return{
      translatedText: ' '
    }
  },
  methods:{
    translateText:function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key='
      //API KEY GOES HERE//
      '&lang=' + language +'&text=' + text)
      .then((response) =>{
        this.translatedText = response.body.text[0];
      })
    }
  }
}
</script>

<style>
body{
  background: #fefefe;
}
</style>
