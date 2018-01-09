<template>
  <div id="translateForm">
    <form v-on:submit ="formSubmit">
        <input type="text" v-model="textToTranslate" placeholder="Enter a word...">
        <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data(){
      return {
          textToTranslate: ''
      }
  },
  methods:{
      formSubmit(e){
          alert('Submitted');
          e.preventDefault();
      }
  }
}
</script>

<style>

</style>
