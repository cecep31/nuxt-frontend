<template>
    <div>hello</div>
    <div>{{ time }}</div>
    <button @click="increment">add</button>
</template>

<script setup>
let time = ref(0)
function increment() {
    time.value++
}

definePageMeta({
    layout: "logged",
});
</script>