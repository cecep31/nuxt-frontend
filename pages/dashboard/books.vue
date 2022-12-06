<template>
    <ol class="list-decimal" v-for="book in books">
        <li>{{ book.title }}|{{book.desc}}</li>
    </ol>

</template>
<script setup>
let token = useCookie("token");

const {data} = await useFetch("https://api.pilput.my.id/api/v1/books", {
    headers: { 
        Authorization: `Bearer ${token.value}`, 
        method: "get"
    }
});
const books = data


// onMounted(() => {

//     var config = {
//         method: 'get',
//         url: 'https://api.pilput.my.id/api/v1/books',
//         headers: {
//             'Authorization': `Bearer ${token.value}`
//         }
//     };

//     axios(config)
//         .then(function (response) {
//             books = response.data
//             console.log(books);
//         })
//         .catch(function (error) {
//             console.log(error);
//         });
// });
</script>