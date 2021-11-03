<template>
    <form>
        <label for="name">Name</label>
        <input
            type="text"
            name="name"
            id="name"
            v-model="_name"
        />
        <label for="job">Job</label>
        <input
            type="text"
            name="job"
            id="job"
            v-model="job"
        />
        <input 
            type="button"
            value="Submit"
            @click="submitForm"
        />
    </form>
</template>

<script setup>
    import { ref, unref } from '@vue/reactivity';
    const _name = ref('')
    const job = ref('')

    const emit = defineEmits(['submit'])

    const submitForm = () => {
        emit('submit', unref(_name), unref(job))
        _name.value = ''
        job.value = ''
    }
</script>

<style>
    form {
        padding: 10px 8px;
    }

    label {
        display: block;
        line-height: 40px;
    }

    input:not(input[type="button"]) {
        display: block;
        width: 320px;
        height: 40px;
        line-height: 40px;
    }

    input[type="button"] {
        margin-top: 20px;
        cursor: pointer;
    }
</style>