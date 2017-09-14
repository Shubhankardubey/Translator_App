<template>
  <div id="app"  class="text-center">
<br/><br/>
<h1>Word Translator</h1>
<p>Powered By Vue.js</p>
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
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText:function(text, language){
    this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170815T174538Z.38d1595ee760408d.5b84364aeeb04fe290ec8d1a32992c9f7545c6a9&lang='+ language +'&text=' + text)
    .then((response) => {
      this.translatedText = response.body.text[0];
    });
    }
  }
}
</script>

<style>
body{
  background: #fefefe;

}
</style>
