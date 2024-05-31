<script setup>

import { ref} from "vue";
const data = ref(null);

const fetchData = () => {
    //make get request using fetch data

    fetch('https://jsonplaceholder.typicode.com/todos/1')
    .then((response) => {
        // check if the response is 0k (200 - 299 range)
        if (!response.ok) {
            throw new Error('HTTP Error! Status: ${response.status');
        }
        //parse the response

        return response.json();
    }).then((responseData) => {
        //set the data to the response
        data.value = responseData;
    }).catch((error) => {
        console.error('Error:', error);
    });
      
}
</script>

<template>
    <div>
        <h1>((Getting Data with Fetch))</h1>
        <button @click="fetchData">Fetch Data</button>
        <div v-if="data">
            <h2>{{data.title}}</h2>
            <pre>{{data}}</pre>
        </div>
    </div>
</template>