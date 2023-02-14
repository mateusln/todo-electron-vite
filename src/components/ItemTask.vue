<script setup lang="ts">

defineProps<{ textValue: string }>()

</script>

<template>
  <p>
    <input type="checkbox">
    <label>{{ textValue }}</label>
  </p>

</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
