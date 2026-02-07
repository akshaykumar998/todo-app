<template>
    <form @submit.prevent="formSubmit">
        <label>
            New Tasks
            <input v-model="newTask" name="newTask">
        </label>
        <div class="form-container" >
            <button>Add</button>
        </div>
    </form>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const newTask = ref("");

const emit = defineEmits<{
    addTask: [newTask: string]
}>();

function formSubmit() {
    if(newTask.value.trim()){
        emit("addTask", newTask.value.trim());
        newTask.value = ""
    }
}

</script>

<style scoped>
    .form-container {
        display: flex;
        justify-content: end;
    }

</style>