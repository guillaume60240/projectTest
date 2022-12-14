<template>
    <div>
        <h1>{{ name }}</h1>
        <p>{{ age }}</p>
    </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';

defineProps<{
    name: string;
    age: number;
}>();
</script>