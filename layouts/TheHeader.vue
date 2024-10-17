<template>
    <div>
        <v-app-bar scroll-behavior="hide" color="teal-lighten-1">
            <v-app-bar-nav-icon variant="text" color="amber-darken-1"
                @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

            <v-app-bar-title class="text-amber-darken-1 font-weight-bold text-h5 cursor-pointer" @click="gotoHome">
                <b>MDBlog</b>
            </v-app-bar-title>
        </v-app-bar>

        <v-navigation-drawer color="amber-lighten-2" v-model="drawer"
            :location="$vuetify.display.mobile ? 'bottom' : undefined" temporary>
            <v-list class="text-teal-darken-3">
                <v-list-item title="MDBlog" subtitle="The story of my life."></v-list-item>
                <v-divider></v-divider>
                <v-list-item to="/" link title="หน้าหลัก"></v-list-item>
                <v-list-item to="/blog/tech" link title="เทคโนโลยี"></v-list-item>
                <v-list-item to="/blog/pets" link title="สัตว์เลื้ยง"></v-list-item>
                <v-list-item to="/about" link title="เกี่ยวกับเรา"></v-list-item>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script>
export default {
    data: () => ({
        drawer: false,
        group: null,
    }),

    watch: {
        group() {
            this.drawer = false
        },
    },

    methods: {
        gotoHome() {
            navigateTo('/')
        }
    }
}
</script>