<script setup>
import { ref} from 'vue'
import ChildComponent from './ChildComponent.vue';
const country = {
    name:'Bangladesh',
    title:'Beautiful country in the world',
    url:'https://en.wikipedia.org/wiki/Bangladesh'
}

const messageToChild = 'This is Child Component'
const messageFromChild = ref('')
</script>
<template>
    <div class="h-screen flex items-center justify-center flex-col">
        <ChildComponent :country = country :messageToChild="messageToChild" v-model:messageFromChild="messageFromChild"></ChildComponent>
        <h1 class="font-bold py-4">Parent Component</h1>
        <h2 class="font-bold">{{ messageFromChild }}</h2>
    </div>
</template>