<template>
    <v-img :aspect-ratio="1" :src="src" :alt="alt" max-height="320" cover>
    </v-img>
</template>

<script setup>
defineProps(['src', 'alt'])
</script>