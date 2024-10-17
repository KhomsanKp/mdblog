<template>
    <v-carousel :show-arrows="false" hide-delimiters cycle class="h-25 my-5">
        <v-carousel-item v-for="(item, i) in data" :src="item.src" :key="i" @click="visitLink(item.link)"
            class="cursor-pointer" cover max-height="350">
        </v-carousel-item>
    </v-carousel>
</template>

<script setup>
defineProps(['data'])
// const items = ref([
//     {
//         src: '/blogs/blog2-1.jpg',
//         link: 'https://s.shopee.co.th/LVI5mxDsy'
//     },
//     {
//         src: '/blogs/blog2-2.jpg',
//         link: 'https://s.shopee.co.th/LVI5mxDsy'
//     }
// ])

async function visitLink(link) {
    await navigateTo(link, { external: true })
}
</script>