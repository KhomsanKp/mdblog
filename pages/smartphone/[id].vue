<template>
    <div>
        <v-sheet class="elevation-1 mt-5 mb-3">
            <h1 class="text-h5 font-weight-bold text-grey-darken-1 pl-6 py-3">รายละเอียด</h1>
        </v-sheet>

        <v-sheet class="d-flex align-center">
            <v-img :src="mobiles.imageUrl" max-height="300" class="w-25" fill />
            <v-spacer></v-spacer>
            <v-sheet class="w-50 text-h6 text-teal-darken-3">
                <h2 class="font-weight-bold text-uppercase">{{ mobiles.brand }} <span>{{ mobiles.model }}</span></h2>
                <div class="border-b mb-3" />

                <v-row no-gutters class="pt-2">

                    <v-col cols="2">
                        <v-icon icon="mdi-cellphone-screenshot" />
                    </v-col>
                    <v-col>
                        <div>
                            <span>{{ mobiles.display.type }}</span>
                            <span>{{ mobiles.display.size }}</span>
                        </div>
                    </v-col>
                </v-row>

                <v-row no-gutters class="pt-1">
                    <v-col cols="2">
                        <v-icon :icon="mobiles.brand === 'Apple' ? 'mdi-apple-ios' : 'mdi-android'" />
                    </v-col>
                    <v-col>
                        <div>
                            <span>{{ mobiles.platform.os }}</span>
                        </div>
                    </v-col>
                </v-row>

                <v-row no-gutters class="pt-1">
                    <v-col cols="2">
                        <v-icon icon="mdi-memory" />
                    </v-col>
                    <v-col>
                        <div class="d-flex flex-column">
                            <span>{{ mobiles.platform.chipset }}</span>
                            <span>{{ mobiles.platform.cpu }}</span>

                            <span>{{ mobiles.platform.gpu }}</span>
                        </div>
                    </v-col>
                </v-row>
            </v-sheet>
        </v-sheet>

        <div class="border-b-lg my-5" />

        <!-- Descriptions -->
        <v-sheet color="teal-lighten-5 pa-5 rounded-lg">
            <v-row no-gutters>
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">เครือข่าย</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        เทคโนโลยี
                        <span class="text-blue pl-3">
                            {{ mobiles.network.technology }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">เปิดคัวครั้งแรก</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        วันที่เปิดตัว <span class="text-blue pl-3">
                            {{ mobiles.launch.announced }}
                        </span>

                        วันทื่ขาย (ประเทศไทย) <span class="text-blue pl-3">
                            {{ mobiles.launch.status }}
                        </span>
                    </div>

                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">ตัวเครื่อง</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ขนาดตัวเครื่อง
                        <span class="text-blue pl-3">
                            {{ mobiles.body.dimensions }}
                        </span>

                        น้ำหนัก
                        <span class="text-blue pl-3">
                            {{ mobiles.body.weight }}
                        </span>

                        วัสดุตัวเครื่อง
                        <span class="text-blue pl-3">
                            {{ mobiles.body.build }}
                        </span>

                        ซิมการ์ด
                        <span class="text-blue pl-3">
                            {{ mobiles.body.sim }}
                        </span>

                        มาตรฐานการกันน้ำกันฝุ่น
                        <span class="text-blue pl-3">
                            {{ mobiles.body.wdstandards }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">จอแสดงผล</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ชนิดหน้าจอ
                        <span class="text-blue pl-3">
                            {{ mobiles.display.type }}
                        </span>

                        ขนาดหน้าจอ
                        <span class="text-blue pl-3">
                            {{ mobiles.display.size }}
                        </span>

                        ความละเอียดหน้าจอ
                        <span class="text-blue pl-3">
                            {{ mobiles.display.resolution }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">แพลตฟอร์ม</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ระบบปฏิบัติการ / เวอร์ขั่น
                        <span class="text-blue pl-3">
                            {{ mobiles.platform.os }}
                        </span>

                        Chipset
                        <span class="text-blue pl-3">
                            {{ mobiles.platform.chipset }}
                        </span>

                        CPU
                        <span class="text-blue pl-3">
                            {{ mobiles.platform.cpu }}
                        </span>

                        GPU
                        <span class="text-blue pl-3">
                            {{ mobiles.platform.gpu }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">กล้องหลัก</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        กล้องหลัง
                        <span class="text-blue pl-3">
                            {{ mobiles.maincamera.main }}
                        </span>

                        ฟีเจอร์
                        <span class="text-blue pl-3">
                            {{ mobiles.maincamera.features }}
                        </span>

                        วิดีโอ
                        <span class="text-blue pl-3">
                            {{ mobiles.maincamera.video }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">
                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">กล้องหน้า</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        กล้องหน้า
                        <span class="text-blue pl-3">
                            {{ mobiles.selfiecamera.main }}
                        </span>

                        ฟีเจอร์
                        <span class="text-blue pl-3">
                            {{ mobiles.selfiecamera.features }}
                        </span>

                        วิดีโอ
                        <span class="text-blue pl-3">
                            {{ mobiles.selfiecamera.video }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">

                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">ระบบเสียง</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ลำโพง
                        <span class="text-blue pl-3">
                            {{ mobiles.sound.loudspeaker }}
                        </span>

                        แจ็คหูฟัง 3.5 มม.
                        <span class="text-blue pl-3">
                            {{ mobiles.sound.jack35mm }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">

                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">การเชื่อมต่อ</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        WiFi
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.wlan }}
                        </span>

                        Bluetooth
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.bluetooth }}
                        </span>

                        GPS
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.positioning }}
                        </span>

                        NFC
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.nfc }}
                        </span>

                        วิทยุ FM
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.radio }}
                        </span>

                        USB
                        <span class="text-blue pl-3">
                            {{ mobiles.comms.usb }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">

                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">คุณสมบัติเพิ่มเติม</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        อื่น ๆ
                        <span class="text-blue pl-3">
                            {{ mobiles.features.sensors }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">

                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">แบตเตอรี่</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ชนิด / ความจุ
                        <span class="text-blue pl-3">
                            {{ mobiles.battery.type }}
                        </span>

                        ชาร์จเร็ว
                        <span class="text-blue pl-3">
                            {{ mobiles.battery.charging }}
                        </span>
                    </div>
                </v-col>
            </v-row>

            <v-row no-gutters class="mt-3">

                <v-col cols="3">
                    <div>
                        <span class="font-weight-bold text-h6 text-teal">อื่น ๆ</span>
                    </div>
                </v-col>

                <v-col>
                    <div class="border-b d-flex flex-column ml-3 text-red text-subtitle-1">
                        ตัวเลือก / สี
                        <span class="text-blue pl-3">
                            {{ mobiles.misc.colors }}
                        </span>

                        รหัสรุ่น
                        <span class="text-blue pl-3">
                            {{ mobiles.misc.model }}
                        </span>

                        ราคาจำหน่าย (ประเทศไทย)
                        <span class="text-blue pl-3">
                            {{ mobiles.misc.price }}
                        </span>
                    </div>
                </v-col>
            </v-row>
        </v-sheet>
    </div>
</template>

<script setup>
const route = useRoute()
const { id } = route.params

const { data: mobiles } = await useAsyncData('mobiles', () => queryContent(id).findOne())

console.log(mobiles.value)
</script>