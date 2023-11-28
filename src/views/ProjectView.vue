<template>
    <p class="mb-3 text-center dark:text-blue-300">Proyectos de <font-awesome-icon icon="fa-brands fa-github" />
    </p>
    <div class="max-h-[50vh] overflow-auto sm:w-4/12 mx-auto">
        <Loader v-if="loading" />
        <div v-if="error" class="text-center text-red-500">{{ error }}</div>
        <div v-for="(project, index) in projects" :key="project.id">
            <a :href="project.html_url" target="_bl">
                <div class="p-2 mb-4 bg-blue-300 rounded-md shadow-md">
                    <h2 class="text-xl font-bold">{{ ++index }} {{ project.name }}</h2>
                    <p>{{ project.description }}</p>
                </div>
            </a>
        </div>
    </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import Loader from '../components/Loader.vue';

const projects = ref([]);
const loading = ref(false);
const error = ref(null);

onMounted(async () => {
    try {
        loading.value = true;
        const res = await fetch('https://api.github.com/users/BiancaRomeroG/repos');
        projects.value = await res.json();
        loading.value = false;
    } catch (ex) {
        error.value = ex;
        loading.value = false;
    }
});

</script>