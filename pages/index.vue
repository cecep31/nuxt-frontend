<template>
    <div>
        <div class="text-red-500">hello</div>
        <HeaderNavbar />
        <div>{{ time }}</div>
        <button @click="increment">add</button>
    </div>
</template>

<script setup>
let time = ref(0)
function increment() {
    time.value++
}
definePageMeta({
    layout: "guest",
});

</script>