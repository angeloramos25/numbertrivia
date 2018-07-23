<template>
  <div id="app" class="row">
    <div class="col-md-6 offset-md-3">
      <form v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="selectedNum" placeholder="Enter a number.">
        <select class="form-control" v-model="category">
          <option value="trivia">Trivia</option>
          <option value="math">Math</option>
          <option value="year">Year</option>
          <option value="date">Date</option>
        </select>
        <input class="btn btn-primary" type="submit" value="Let's Go!">
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'NumberForm',
  data() {
    return {
      selectedNum: '',
      category: ''
    }
  },
  created() {
    this.category = 'trivia'
  },
  methods: {
    formSubmit(event) {
      this.$emit('formSubmit', this.selectedNum, this.category);
      event.preventDefault();
    }
  }
}
</script>

<style>

.form-control {
  margin-top: 30px;
}

.btn {
  margin-top: 30px;
}

</style>
