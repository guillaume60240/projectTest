<template>
    <ion-button @click="() => {router.push(`/${link}`);}">{{ label }}</ion-button>
</template>

<script setup lang="ts">
import { IonButton } from '@ionic/vue';
import { useRouter } from "vue-router";
import { defineProps } from 'vue';

const router = useRouter();

defineProps<{
    link: string;
    label: string;
}>();
</script>