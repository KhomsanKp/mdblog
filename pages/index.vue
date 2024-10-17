<template>
    <v-card variant="text">
        <template #title>
            <h1 class="text-h5 font-weight-bold">บทความ</h1>
        </template>
        <BlogList :blogs-list="blogs" />
    </v-card>
</template>

<script setup>
const { data: blogs } = await useAsyncData('blogs', () => queryContent('/_blogs').find())
</script>