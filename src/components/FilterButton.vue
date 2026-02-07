<template>
    <button class="secondary" 
        @click="emits('setFilter', filter)"
        :class="{
            contrast: currentFilter === filter
        }"
        >
        {{ filter.toLocaleUpperCase() }}
    </button>
</template>

<script lang="ts" setup>
import type { TaskFilter } from '../types';

defineProps<{
    filter: TaskFilter,
    currentFilter: TaskFilter
}>();

const emits = defineEmits<{
    setFilter: [filter: TaskFilter]
}>();
</script>

