<template>
    <v-footer class="bg-amber-lighten-2">
        <v-row justify="center" no-gutters>
            <v-btn v-for="(link, idx) in links" :key="idx" :to="link.value" class="mx-2" color="amber" variant="text"
                rounded="xl">
                <span class="text-teal">
                    {{ link.label }}
                </span>
            </v-btn>
            <v-col class="text-center mt-4" cols="12">
                copy right {{ new Date().getFullYear() }} by <strong>MDBlog</strong>
            </v-col>
        </v-row>
    </v-footer>
</template>

<script>
export default {
    data: () => ({
        links: [
            {
                label: 'หน้าหลัก',
                value: '/'
            },
            {
                label: 'เกี่ยวกับเรา',
                value: '/about'
            },
        ],
    }),
}
</script>