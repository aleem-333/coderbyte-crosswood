<template>
  <div class="row w-100 m-0 p-2 bg-dark-500">
    <form-widget class="col-md-6 p-2"></form-widget>
    <preview-widget class="col-md-6 p-2"></preview-widget>
  </div>
</template>

<script>
import FormWidget from './FormWidget.vue'
import PreviewWidget from './PreviewWidget.vue'

export default {
  components: { FormWidget, PreviewWidget },
  name: 'HomeComponent',
}
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
