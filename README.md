# Vue.js Word Translator

A word translator built with Vue.js that uses the <a href="https://tech.yandex.com/translate/">Yandex Translate API</a>. To run this application, you'll need to sign up for a key and place paste it in `src/App.vue` in the export method (see below).

```
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
```

The application currently translate English to Russian, Spanish, French, German, Arabic, Italian, Hebrew and Swedish.

I followed this <a href="https://www.youtube.com/watch?v=DBADrF0C2ls">video</a> as a guide as I'm trying to get more familiar with the Vue.js framework. All styling was done using <a href="https://bootswatch.com/flatly/"> Bootswatch's Flatly Theme</a>.

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
