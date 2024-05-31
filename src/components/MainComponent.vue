<script setup>
import { ref } from 'vue'
import ComponentOne from './ComponentOne.vue'
import ComponentTwo from './ComponentTwo.vue'
import ComponentThree from './ComponentThree.vue'


const currentComponent = ref('ComponentOne')

const component = {
    ComponentOne,
    ComponentTwo,
    ComponentThree

}
</script>


<template>
    <button @click="currentComponent = 'ComponentOne'">what is Html</button>
    <button @click="currentComponent = 'ComponentTwo'">what is css</button>
    <button @click="currentComponent = 'ComponentThree'">what is javascript</button> 

    <!-- Dynamic Component -->

    <component :is="component[currentComponent]" />

</template>