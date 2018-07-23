<template>
  <div id="app" class="row text-center">
    <div class="col-md-6 offset-md-3">
      <h2>Number Trivia</h2>
      <h5>Powered by Vue.js and the Numbers API.</h5>
      <NumberForm v-on:formSubmit="getFact"></NumberForm>
      <NumberOutput v-text="funFact"></NumberOutput>
    </div>
  </div>
</template>

<script>
import NumberForm from './components/NumberForm'
import NumberOutput from './components/NumberOutput'

export default {
  name: 'App',
  components: {
    NumberForm,
    NumberOutput
  },
  data() {
    return {
      funFact: ''
    }
  },
  methods: {
    getFact: function(number,category) {
      this.$http.get('http://numbersapi.com/' + number + '/' + category)
      .then(response => {
        this.funFact = response.body;
      });
    }
  }
}
</script>

<style>

body {
  margin-top: 40px;
  font-family: 'Avenir';
  background: #2d2d2d;
}

@font-face {
  font-family: Avenir;
  src: url(https://www.wfonts.com/download/data/2016/06/21/avenir/AEH.ttf);
}

</style>
