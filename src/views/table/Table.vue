<template>
    <table>
        <table-header></table-header>
        <table-body :characterData="characterData" @delete="handleDelete"></table-body>        
    </table>
</template>

<script setup>
import TableHeader from './components/TableHeader.vue';
import TableBody from './components/TableBody.vue';

const props = defineProps({
    characterData: Array
})

const emit = defineEmits(['delete'])

const handleDelete = (index) => {
    console.log('table index==>', index)
    emit('delete', index)
}
</script>

<style>
table {
  width: 100%;
}

tr {
  line-height: 40px;
  text-align: left;
}

th, td {
  padding: 5px 8px;
  border-bottom: 1px solid #e1e1e1;
}

button {
    cursor: pointer;
}
</style>