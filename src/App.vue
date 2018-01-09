<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h4>Powered By Vue.js</h4>
    <TranslateForm></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'

export default {
  name: 'app',
  components: {
    TranslateForm
  }
}
</script>

<style>
#app {

}
</style>
