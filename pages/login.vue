<template>
    <main class="dark:bg-gray-800 bg-white relative overflow-hidden h-screen">
        <div class="min-h-screen flex justify-center items-center">
            <div class="absolute w-60 h-60 rounded-xl bg-black -top-5 -left-16 z-0 transform rotate-45 hidden md:block">
            </div>
            <div class="absolute w-48 h-48 rounded-xl bg-black -bottom-6 -right-10 transform rotate-12 hidden md:block">
            </div>
            <div class="py-12 px-12 bg-white rounded-2xl shadow-xl z-20">
                <form @submit.prevent="loginnya">


                    <div>
                        <h1 class="text-3xl font-bold text-center mb-4 cursor-pointer">
                            Sign in
                        </h1>
                        <p
                            class="w-80 text-center text-sm mb-8 font-semibold text-gray-700 tracking-wide cursor-pointer">
                            lanjut aja login ngapain baca
                        </p>
                    </div>
                    <div class="space-y-4">
                        <input type="text" placeholder="Username" v-model="username"
                            class="block text-sm py-3 px-4 rounded-lg w-full border outline-none" />
                        <input type="password" placeholder="Password" v-model="password"
                            class="block text-sm py-3 px-4 rounded-lg w-full border outline-none" />
                    </div>
                    <div class="text-center mt-6">
                        <button class="py-3 w-64 text-xl text-white bg-gray-800 hover:bg-gray-900 rounded-2xl">
                            Login
                        </button>
                    </div>
                </form>
            </div>
            <div class="w-40 h-40 absolute bg-black rounded-full top-0 right-12 hidden md:block"></div>
            <div class="w-20 h-40 absolute bg-black rounded-full bottom-20 left-10 transform rotate-45 hidden md:block">
            </div>
        </div>
    </main>
</template>
<script setup>
import axios from 'axios'

const router = useRouter();
const username = ref("");
const password = ref("");

async function loginnya() {
    var data = JSON.stringify({
        identity: username.value,
        password: password.value,
    });

    var config = {
        method: "post",
        url: "https://api.pilput.my.id/api/auth/login",
        headers: {
            'Content-Type': 'application/json'
        },
        data: data,
    };
   
    try {
        const response = await axios(config);
        alert(response.data.data)
        router.replace({path:"/dashboard"});
    } catch (error) {
        console.log(error);
        alert("Username or password is wrong");
    }

}

definePageMeta({
    layout: "guest",
});
</script>