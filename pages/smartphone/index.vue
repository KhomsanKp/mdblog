<template>
    <div>
        <v-sheet class="elevation-1 mt-5 mb-3">
            <h1 class="text-h4 font-weight-bold text-grey-darken-1 pl-6 py-3">Smartphone</h1>
        </v-sheet>

        <v-card variant="text">
            <h2 class="text-h5 font-weight-bold my-5 w-100 bg-teal-lighten-4 rounded-lg pl-5 py-2">Apple</h2>

            <SmartphoneList v-if="iphone.length > 0" :item-list="iphone" />

            <v-sheet v-else class="w-100 py-10 text-center bg-amber-lighten-5 rounded-lg">
                <p>No documents</p>
            </v-sheet>
        </v-card>

        <v-card variant="text">
            <h2 class="text-h5 font-weight-bold my-5 w-100 bg-teal-lighten-4 rounded-lg pl-5 py-2 text-blue-darken-3">
                Samsung
            </h2>

            <SmartphoneList v-if="galaxy.length > 0" :item-list="galaxy" />

            <v-sheet v-else class="w-100 py-10 text-center bg-amber-lighten-5 rounded-lg">
                <p>No documents</p>
            </v-sheet>
        </v-card>

        <v-card variant="text">
            <h2 class="text-h5 font-weight-bold my-5 w-100 bg-teal-lighten-4 rounded-lg pl-5 py-2 text-orange">Xiaomi
                Redmi Poco
            </h2>

            <SmartphoneList v-if="xmphone.length > 0" :item-list="xmphone" />
            <v-sheet v-else class="w-100 py-10 text-center bg-amber-lighten-5 rounded-lg">
                <p>No documents</p>
            </v-sheet>
        </v-card>

        <v-card variant="text">
            <h2 class="text-h5 font-weight-bold my-5 w-100 bg-teal-lighten-4 rounded-lg pl-5 py-2 text-blue-darken-1">
                Oppo Vivo Realme
                OnePlus
            </h2>

            <SmartphoneList v-if="xmphone.length > 0" :item-list="xmphone" />
            <v-sheet v-else class="w-100 py-10 text-center bg-amber-lighten-5 rounded-lg">
                <p>No documents</p>
            </v-sheet>
        </v-card>

    </div>
</template>

<script setup>
import SmartphoneList from '~/components/SmartphoneList.vue';

const { data: iphone } = await useAsyncData('apple', () => queryContent('_smartphone', 'apple', 'iphone').find())
const { data: galaxy } = await useAsyncData('galaxy', () => queryContent('_smartphone', 'samsung', 'galaxyphone').find())
const { data: xmphone } = await useAsyncData('xmphone', () => queryContent('_smartphone', 'xiaomi', 'phone').find())

</script>