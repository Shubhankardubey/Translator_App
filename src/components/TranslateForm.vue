<template>
  <div class="row" id="translateForm">
    <div class="col-md-6 col-md-offset-3">
<form class="well form-inline" id="transForm" v-on:submit="formSubmit">
  <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word.....">
<select class="form-control" v-model="language">
<option value="ru">Russian</option>
<option value="es">Spanish</option>
<option value="fr">French</option>
<option value="zh">Chinese</option>
<option value="bn">Bengali</option>
<option value="nl">Dutch</option>
<option value="el">Greek</option>
<option value="it">Italian</option>
<option value="gu">Gujarati</option>
<option value="mr">Marathi</option>
<option value="di">German</option>
<option value="ne">Nepali</option>
<option value="pa">Punjabi</option>
<option value="ta">Tamil</option>
<option value="te">Telgu</option>
<option value="hi">Hindi</option>
<option value="gd">Scottish</option>
</select>
  <input class="btn btn-primary" type="submit" value="Translate">

</form>
  </div>
</div>
</template>

<script>
export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate: '',
      languge:''
    }
  },
  created(){
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }

}
</script>

<style>
#transForm {
border-radius: 10px;
border: 1px solid #ccc;

}
</style>
