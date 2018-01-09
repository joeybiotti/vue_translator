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
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180109T024328Z.5f75f3e36c93c3d0.d0bbb29d3662d2cabe88b172e2f95544eef71f71&lang=' + language +'&text=' + text)
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
