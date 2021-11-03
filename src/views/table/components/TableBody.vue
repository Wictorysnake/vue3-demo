<template>
    <tbody>
        <tr v-for="(row, index) in characterData" :key="index">
            <td>{{row.name}}</td> 
            <td>{{row.job}}</td>
            <td>
                <button @click="handleDelete(index)">Delete</button>
            </td>
        </tr>
    </tbody>
</template>

<script setup>
    const props = defineProps({
        characterData: Array
    })

    const emit = defineEmits(['delete'])

    const handleDelete = (index) => {
        console.log('body index==>', index)
        emit('delete', index)
    }
</script>