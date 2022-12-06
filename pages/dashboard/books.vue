<template>
    <ol v-for="book in books">
        <li >{{book.title}}</li>
    </ol>
  
</template>
<script setup>
import axios from 'axios';

let books;
let token = useCookie("token");


onMounted(() => {

    var config = {
        method: 'get',
        url: 'https://api.pilput.my.id/api/v1/books',
        headers: {
            'Authorization': `Bearer ${token.value}`
        }
    };

    axios(config)
        .then(function (response) {
            books = response.data
            console.log(books);
        })
        .catch(function (error) {
            console.log(error);
        });
});
</script>