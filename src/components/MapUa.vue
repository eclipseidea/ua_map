<template>
    <div style="height: 350px;">
        <div class="info" style="height: 15%;">
            {{this.active_city}}
        </div>
        <l-map
                style="height: 100%; width: 100%; "
                :zoom="zoom"
                :center="center">

            <l-tile-layer :url="url"></l-tile-layer>

            <l-circle @click="click(1)"
                      :lat-lng="coordinates.kiev"
                      :radius="circle.radius"
                      :color="circle.color">
                <l-popup>
                    {{active_city + active_marker}}
                </l-popup>
            </l-circle>

            <l-circle @click="click(2)"
                      :lat-lng="coordinates.lviv"
                      :radius="circle.radius"
                      :color="circle.color">
                <l-popup>
                    {{active_city + active_marker}}
                </l-popup>
            </l-circle>

            <l-circle @click="click(3)"
                      :lat-lng="coordinates.donetsk"
                      :radius="circle.radius"
                      :color="circle.color">
                <l-popup>
                    {{active_city + active_marker}}
                </l-popup>
            </l-circle>

            <l-circle @click="click(4)"
                      :lat-lng="coordinates.odesa"
                      :radius="circle.radius"
                      :color="circle.color">
                <l-popup>
                    {{active_city + active_marker}}
                </l-popup>
            </l-circle>

            <l-circle @click="click(5)"
                      :lat-lng="coordinates.dnipro"
                      :radius="circle.radius"
                      :color="circle.color">
                <l-popup>
                    {{active_city + active_marker}}
                </l-popup>
            </l-circle>

        </l-map>
    </div>
</template>

<script>
    import {LMap, LTileLayer, LCircle,LPopup} from 'vue2-leaflet';

    export default {
        components: {
            LCircle,
            LMap,
            LTileLayer,
            LPopup
        },
        data() {
            return {
                url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
                zoom: 5,
                center: [48.965794, 35.595703],
                bounds: null,

                circle: {
                    radius: 9500,
                    color: 'blue'
                },

                active_city: null,
                active_marker: null,

                coordinates: {
                    lviv: [49.828682, 24.052771],
                    kiev: [50.450728, 30.548515],
                    odesa: [48.018635, 37.786102],
                    donetsk: [46.48356, 30.739059],
                    dnipro: [48.484756, 35.131187]
                }
            };
        },
        methods: {
            click(val) {
                switch (val) {
                    case 1:
                        this.active_city = 'Kiev'
                        this.active_marker = this.coordinates.kiev
                        break
                    case 2:
                        this.active_city = 'Lviv'
                        this.active_marker = this.coordinates.lviv
                        break
                    case 3:
                        this.active_city = 'Odesa'
                        this.active_marker = this.coordinates.odesa
                        break
                    case 4:
                        this.active_city = 'Donetsk'
                        this.active_marker = this.coordinates.donetsk
                        break
                    case 5:
                        this.active_city = 'Dnipro'
                        this.active_marker = this.coordinates.dnipro
                        break
                    default:
                        this.active_city = null
                        this.active_marker = null
                        break
                }
            }
        },

    }
</script>
