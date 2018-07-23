<template>
  <h5>{{funFact}}</h5>
</template>

<script>

export default {
  name: 'NumberOutput',
  props: [
    'funFact'
  ]
}
</script>

<style>

h5 {
  margin-top: 30px;
}

</style>
