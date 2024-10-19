<template>
  <v-data-iterator :items="props.itemList" :page="page" :items-per-page="10">
    <template v-slot:default="{ items }">
      <v-row dense>
        <v-col v-for="(item, i) in items" :key="i" cols="auto" md="3">
          <v-card class="pb-3" border flat>
            <v-img :src="item.raw.imageUrl" />

            <v-list-item :subtitle="item.raw.model">
              <template v-slot:title>
                <strong class="text-h6 mb-2">{{ item.raw.brand }}</strong>
              </template>
            </v-list-item>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </v-data-iterator>
</template>

<script setup>
const props = defineProps(['itemList'])

const page = ref(1)
// const items = ref([
//   {
//     img: 'https://cdn.vuetifyjs.com/docs/images/graphics/games/4.png',
//     title: 'The Sci-Fi Shooter Experience',
//     subtitle: 'Dive into a futuristic world of intense battles and alien encounters.',
//     advanced: false,
//     duration: '8 minutes',
//   },
//   {
//     img: 'https://cdn.vuetifyjs.com/docs/images/graphics/games/2.png',
//     title: 'Epic Adventures in Open Worlds',
//     subtitle: 'Embark on a journey through vast, immersive landscapes and quests.',
//     advanced: true,
//     duration: '10 minutes',
//   },
//   {
//     img: 'https://cdn.vuetifyjs.com/docs/images/graphics/games/3.png',
//     title: 'Surviving the Space Station Horror',
//     subtitle: 'Navigate a haunted space station in this chilling survival horror game.',
//     advanced: false,
//     duration: '9 minutes',
//   },
// ])
</script>