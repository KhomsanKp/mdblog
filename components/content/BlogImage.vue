<template>
    <v-img :aspect-ratio="1" :src="imageSrc" :alt="imageAlt" max-height="350" cover>
    </v-img>
</template>

<script setup>
defineProps(['imageSrc', 'imageAlt'])
</script>