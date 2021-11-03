<template>
  <div class="container">
    <Table :characterData="characters" @delete="removeCharacter" />
    <Form @submit="handleSubmit" />
  </div>
</template>

<script setup>
import { reactive } from '@vue/reactivity';
import Table from './views/table/Table.vue';
import Form from './views/form/Form.vue';

let characters = reactive([
  {
    name: 'Charlie',
    job: 'Janitor'
  },
  {
    name: 'Mac',
    job: 'Bouncer'
  },
  {
    name: 'Dee',
    job: 'Aspring actress'
  },
  {
    name: 'Dennis',
    job: 'Bartender'
  }
])

const removeCharacter = (index) => {
  console.log('app index==>', index)
  characters.splice(index, 1)
  console.log(characters)
}

const handleSubmit = (name, job) => {
  console.log(name, job)
  characters.push({
    name,
    job
  })
}

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
</script>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}
</style>
