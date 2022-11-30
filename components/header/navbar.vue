<template>
    <div className="container mx-auto px-6 flex items-center justify-between">
        <div className="uppercase text-gray-800 dark:text-white font-black text-3xl">
            pilput
        </div>
        <div className="flex items-center">
            <nav className="font-sen text-gray-800 dark:text-white uppercase text-lg lg:flex items-center hidden">
                <NuxtLink href="/" className="py-2 px-6 flex text-indigo-500 border-b-2 border-indigo-500">
                    Home
                </NuxtLink>
                <NuxtLink href="#about" className="py-2 px-6 flex hover:text-indigo-500">
                    about
                </NuxtLink>
                <NuxtLink href="#product" className="py-2 px-6 flex hover:text-indigo-500">
                    social
                </NuxtLink>
            </nav>
            <button className="lg:hidden flex flex-col ml-4">
                <span className="w-6 h-1 bg-gray-800 dark:bg-white mb-1"></span>
                <span className="w-6 h-1 bg-gray-800 dark:bg-white mb-1"></span>
                <span className="w-6 h-1 bg-gray-800 dark:bg-white mb-1"></span>
            </button>
        </div>
        <div>
            <NuxtLink href="/dashboard" className="bg-gray-500 px-5 py-2 rounded-lg hover:bg-gray-600 text-white">
                Dashboard
            </NuxtLink>

            <NuxtLink href="/login" className="bg-blue-500 px-5 py-2 rounded-lg hover:bg-blue-600 text-white">
                Login
            </NuxtLink>
        </div>
    </div>
</template>