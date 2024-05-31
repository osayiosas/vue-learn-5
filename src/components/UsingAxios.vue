<script setup>
import {ref} from "vue";
import axios from 'axios'


const data = ref(null);


const  fetchData = async  () => {
    try {
        //make a get request to axios

        const response = await axios.get('https://jsonplaceholder.typicode.com/posts')

        //set the data to the response 

        data.value = response.data
    } catch (error) {
        console.error(`Error fetching data: ${error}`);
    }
    }

</script>

<template>
    <h1>((Axios))</h1>

    <button @click="fetchData">Fetch Data</button>

    <div>
        <!-- <ul>
            <li v-for="item in data" :key="item.id">
                <h2>((item.title))</h2>
                <p>((item.body))</p>
            </li>
        </ul> -->
        <h2>API Data:</h2>
        <pre>{{ data }}</pre>
    </div>
</template>