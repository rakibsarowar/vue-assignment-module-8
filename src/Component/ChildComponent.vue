<script setup>
import { defineProps } from 'vue';

defineProps(['country', 'messageToChild', 'messageFromChild'])
defineEmits(['update:messsageFromChild'])
</script>
<template>
    <div class="p-5 border border-gray-300">
        <div class="max-w-lg mx-auto p-4 bg-white rounded-md flex flex-col items-center justify-center">
            <h1 class="text-2xl font-bold text-black-900">
                {{ messageToChild }}
            </h1>
        </div>

        <div class="max-w-md mx-auto p-6 bg-white rounded-md flex flex-col items-center justify-center">
            <div class="flex flex-col items-center justify-center pt-5 pb-5">
                <p class="text-lg font-semibold">{{ country.name }}</p>
                <p class="text-sm text-gray-500">{{ country.title }}</p>
            </div>
            <div class="flex gap-2">
                <button @click="$emit('update:messageFromChild',country.url)" class="bg-yellow-600 py-1 px-4  text-white font-bold hover:bg-yellow-600">Click to learn</button>
                <button @click="$emit('update:messageFromChild','')" class="bg-yellow-600 py-1 px-4  text-white font-bold hover:bg-yellow-600">Hide</button>
            </div>
        </div>
    </div>
</template>