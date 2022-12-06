<template>
    index
    <div>
        
    </div>
</template>
<script setup>
const { session } = await useSession()
let token;
token = useCookie("token");



onMounted(() => {
    console.log(token.value);
})


</script>