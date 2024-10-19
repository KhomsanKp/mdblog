<template>
    <div>
        <v-app-bar scroll-behavior="hide" color="teal">
            <v-app-bar-nav-icon variant="text" color="amber-darken-1"
                @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

            <v-app-bar-title class="text-amber font-weight-bold text-h5 cursor-pointer" @click="gotoHome">
                <b>MDBlog</b>
            </v-app-bar-title>
        </v-app-bar>

        <v-navigation-drawer color="teal-lighten-4" v-model="drawer"
            :location="$vuetify.display.mobile ? 'bottom' : undefined" temporary>
            <!-- <v-list>
                <v-list-item title="MDBlog" subtitle="The story of my life."
                    class="text-amber-darken-1 border-b"></v-list-item>
                <v-divider></v-divider>
                <v-list-item to="/" link title="หน้าหลัก"></v-list-item>
                <v-list-item to="/blog/tech" link title="เทคโนโลยี"></v-list-item>
                <v-list-item to="/blog/pets" link title="สัตว์เลื้ยง"></v-list-item>
                <v-list-item to="/blog/smartphone" link title="Smartphone"></v-list-item>
                <v-list-item to="/about" link title="เกี่ยวกับเรา"></v-list-item>
            </v-list> -->

            <v-list :opened="open">
                <v-list-item to="/" prepend-icon="mdi-home" title="หน้าหลัก"></v-list-item>

                <v-list-group value="Blogs">
                    <template v-slot:activator="{ props }">
                        <v-list-item v-bind="props" prepend-icon="mdi-post" title="บทความ"></v-list-item>
                    </template>

                    <v-list-item v-for="([title, icon, link], i) in blogList" :key="i" :prepend-icon="icon"
                        :title="title" :to="link" :value="title"></v-list-item>
                </v-list-group>

                <v-list-group value="Smartphone">
                    <template v-slot:activator="{ props }">
                        <v-list-item v-bind="props" prepend-icon="mdi-cellphone" title="Smartphone"></v-list-item>
                    </template>

                    <v-list-item v-for="([title, icon, link], i) in smartphoneList" :key="i" :prepend-icon="icon"
                        :title="title" :to="link" :value="title"></v-list-item>
                </v-list-group>

                <!-- <v-list-item to="/about" prepend-icon="mdi-home" title="เกี่ยวกับเรา"></v-list-item> -->
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script>
export default {
    data: () => ({
        drawer: false,
        group: null,
        open: ['Blogs'],
        blogList: [
            ['เทคโนโลยี', 'mdi-account-multiple-outline', '/blog/tech'],
            ['สมาร์ทโฟน', 'mdi-cellphone', '/blog/smartphone'],
            ['สัตว์เลี้ยง', 'mdi-paw', '/blog/pets'],
        ],
        smartphoneList: [
            ['All brand', 'mdi-paw', '/smartphone'],
            ['Apple', 'mdi-account-multiple-outline', '/smartphone/apple'],
            ['Samsung', 'mdi-cellphone', '/smartphone/samsung'],
        ],
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