<template>
    <div class="">
        <ul class="flex justify-center">
            <li>
                <RouterLink to="/"
                    class="px-4 py-2 m-1 border-2 border-blue-600 rounded-full hover:bg-blue-600 hover:text-white hover:transition-all hover:duration-300 dark:text-white ">
                    Home</RouterLink>
                <RouterLink to="/about"
                    class="px-4 py-2 m-1 border-2 border-blue-600 rounded-full hover:bg-blue-600 hover:text-white hover:transition-all hover:duration-300 dark:text-white">
                    Acerca de</RouterLink>
                <RouterLink to="/project"
                    class="px-4 py-2 m-1 border-2 border-blue-600 rounded-full hover:bg-blue-600 hover:text-white hover:transition-all hover:duration-300 dark:text-white">
                    Proyectos</RouterLink>
            </li>
        </ul>


        <div>
            <hr class="mx-auto my-8 border-gray-400 border-1 sm:w-4/12">
        </div>
    </div>
</template>
<script setup>
import router from '../router';

const route = router.currentRoute.value.path;
</script>