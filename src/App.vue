<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

import ItemTask from './components/ItemTask.vue';
import InputTask from './components/InputTask.vue';
import { ref } from 'vue';

const getStoredItems = () => ["comprar leite", "comprar pão", "comprar carne", "comprar frutas"]
const items = ref(getStoredItems())

const addTask = (taskDesc: string) => {
    if (taskDesc.length === 0)
        return

    items.value.push(taskDesc)
}

</script>

<template>
    <ItemTask :textValue="item" v-for="item in items" />
    <InputTask @on-add-task="(val) => addTask(val)" />

    <!-- <div class="static-public"> -->
    <!--     Place static files into the <code>/public</code> folder -->
    <!-- </div> -->
</template>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
    color: #2c3e50;
    margin-top: 60px;
}

.logo-box {
    display: flex;
    width: 100%;
    justify-content: center;
}

.static-public {
    display: flex;
    align-items: center;
    justify-content: center;
}

.static-public code {
    background-color: #eee;
    padding: 2px 4px;
    margin: 0 4px;
    border-radius: 4px;
    color: #304455;
}

.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: 0.75s;
}

.logo.vite:hover {
    filter: drop-shadow(0 0 2em #747bff);
}

.logo.electron:hover {
    filter: drop-shadow(0 0 2em #9FEAF9);
}

.logo.vue:hover {
    filter: drop-shadow(0 0 2em #249b73);
}
</style>
