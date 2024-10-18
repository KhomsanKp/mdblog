<template>
    <div>
        <v-sheet class="elevation-1 bg-amber-lighten-5 mt-5 mb-3" rounded="lg">
            <h1 class="text-h5 font-weight-bold text-amber pl-6 py-3">บทความ</h1>
        </v-sheet>

        <BlogList :blogs-list="blogs" />

        <v-container class="my-3">
            <v-sheet>
                <ContentDoc path="/advert/advert1" />
            </v-sheet>
        </v-container>

    </div>
</template>

<script setup>
const { data: blogs } = await useAsyncData('blogs', () => queryContent('/_blogs').find())

console.log(blogs.value)

useHead({
    title: 'MDBblog',
    meta: [
        { name: 'title', content: 'MDBlog' },
        { name: 'description', content: 'MDBlog เว็บบล็อกไอที เทคโนโลบี สัตวเลี่้ยง ไลฟ์สไตส์ อื่นๆ' },
        { name: 'author', content: "Bird348" }
    ]
})
</script>