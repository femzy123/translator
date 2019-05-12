<template>
  <div id="app" class="text-center">
    <h1 class>Word Translator</h1>
    <h5>Powered by Vue.Js</h5>
    <TranslateForm v-on:formSubmit="translateText" />
    <TranslateOutput v-text="translatedText"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data() {
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText:function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190511T223011Z.6f28be3cf87bd4f9.888326a74cb5751fb7ddd1903d653c22bf5ee3b8&lang='+language+'&text='+text)
      .then((response)=> {
        this.translatedText = response.body.text[0];
      });
    }
  }
}
</script>

<style>
body {
  background: #fefefe;
}
</style>
