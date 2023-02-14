<script setup lang="ts">
import { ref } from 'vue';

const emit = defineEmits(['onAddTask'])
let text = ref();

// defineProps<{ textValue: string }>()

function emitSignalOnAddTask() {
    emit('onAddTask', text.value)
    text.value = ''
}

</script>

<template>

    <input id="textToSave" name="textToSave" v-model.trim="text" @keyup.enter="emitSignalOnAddTask()">
    <button type="button" @click="emitSignalOnAddTask()">Add Task </button>

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
