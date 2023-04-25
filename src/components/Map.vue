<template>
    <div class="app">
        <div class="leftSidebar" :class="[sidebarFlag === 0 ? 'sidebarHidden' : '']">
            <div id="sideBar">
                <div class="locationData" v-for="(item, index) in position" :key="index"
                    @click="setCenterByLocation(item.id, index)">
                    <div class="headInfo">
                        <h3 class="locationNumber magSize" style=" cursor: pointer;">
                            {{ item.popup.hotelName }}
                        </h3>
                        <h4>●</h4>
                        <h3 class="locationNumber fw-300" style=" cursor: pointer;">
                            Boş Oda: {{ item.popup.freeRoomCount }}</h3>
                        <h4>●</h4>
                        <h3 class="locationNumber fw-300" style=" cursor: pointer;">
                            Dolu Oda: {{ item.popup.busyRoomCount }}
                        </h3>
                    </div>
                    <div>
                        <div class="lastLocationData">
                            <p class="locationAddress" style=" cursor: pointer;">

                            </p>

                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div id="mapBox">
            <l-map :zoom="zoom" :center="center" :min-zoom="minZoom" :max-zoom="maxZoom" ref="map">
                <l-tile-layer :url="mapCreator" :attribution="attribution" />
                <l-marker v-for="(item, index) in position" :key="index" :lat-lng="item.position"
                    @click="() => center = [item.position.lat, item.position.lng]">
                    <l-popup>
                        <div class="magnitude">
                            <h2 style="font-size: 20px;color: #446c8f;;">{{ item.popup.hotelName }}</h2>
                            <h4>{{ item.popup.hotelStatus }}</h4>
                        </div>
                        <div class="infos">
                            <h5>Boş Oda: {{ item.popup.freeRoomCount }}</h5>
                            <h5>Dolu Oda: {{ item.popup.busyRoomCount }}</h5>

                        </div>
                    </l-popup>
                    <l-icon>
                        <div :id="item.id">
                            <svg style="color: #2a79db;filter: drop-shadow(0px 0px 17px );background-color: white;"
                                xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                                class="bi bi-h-square-fill" viewBox="0 0 16 16">
                                <path
                                    d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2Zm9 4.002V12H9.67V8.455H6.33V12H5V4.002h1.33v3.322h3.34V4.002H11Z" />
                            </svg>
                        </div>
                    </l-icon>
                    
                </l-marker>
                <l-icon-default />
            </l-map>
        </div>
    </div>
</template>
  
<script>
import { LMap, LTileLayer, LMarker, LIconDefault, LPopup, LIcon, } from "vue2-leaflet";
import "leaflet/dist/leaflet.css"

let cityId
export default {
    components: {
        LMap,
        LTileLayer,
        LMarker,
        LIconDefault,
        LPopup,
        LIcon,
       
    },
    data() {
        return {
            zoom: 4,
            minZoom: 4,
            maxZoom: 15,
            path: "/images/",
            center: [36.547591, 31.982151],
            popupOpen: "",
            attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
            citySearch: '',
            searchArray: [],
            sidebarFlag: 1,
            mapCreator: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
            position: [],
        };
    },
    mounted() {
        this.position = [
            { position: { lat: 36.547591, lng: 31.982151 }, id: 0, popup: { hotelName: "Hotel Ktun", freeRoomCount: 120, busyRoomCount: 112, hotelStatus: "Normal" } },
            { position: { lat: 36.557157, lng: 31.965767 }, id: 1, popup: { hotelName: "Hotel Antalya", freeRoomCount: 160, busyRoomCount: 134, hotelStatus: "Sessiz" } },
            { position: { lat: 36.766682, lng: 31.389935 }, id: 2, popup: { hotelName: "Hotel Konyalı", freeRoomCount: 123, busyRoomCount: 163, hotelStatus: "Sessiz" } },
            { position: { lat: 36.820561, lng: 31.283972 }, id: 3, popup: { hotelName: "Hotel Meram", freeRoomCount: 198, busyRoomCount: 127, hotelStatus: "Normal" } },
            { position: { lat: 36.598774, lng: 30.564585 }, id: 4, popup: { hotelName: "Hotel Side", freeRoomCount: 132, busyRoomCount: 129, hotelStatus: "Kalabalık" } },
            { position: { lat: 36.674043, lng: 30.555277 }, id: 5, popup: { hotelName: "Hotel Kemer", freeRoomCount: 137, busyRoomCount: 142, hotelStatus: "Kalabalık" } },

        ]

        let leafletZoom = document.querySelector(".leaflet-left")
        leafletZoom.remove()
    },


    watch: {
        //   citySearch() {

        //     this.filterCity()

        //   }
    },
    methods: {
        sidebarHide() {
            if (this.sidebarFlag != 0) {
                this.sidebarFlag = 0
            }
            else {
                this.sidebarFlag = 1
            }
        },
        filterCity() {
            this.searchArray[0] = this.getDetailData[0]
            this.searchArray[0] = this.searchArray[0].filter(item => item.title.toLowerCase().includes(this.citySearch.toLowerCase()))
        },
        setCenterByLocation(id) {

            cityId = this.position.filter((item) => item.id === id)
            setTimeout(async () => {

                await this.$refs.map.mapObject.flyTo(cityId[0].position, 13, { duration: 3.2 })
            }, 10);
            setTimeout(() => {
                this.x = document.querySelectorAll(`.leaflet-marker-icon`)
                Array.from(this.x).map((item) => {

                    if (item.childNodes[0].getAttribute("id") === JSON.stringify(cityId[0].id)) {

                        item.childNodes[0].click()
                    }
                })
            }, 3300);
        },

    }
};


</script>
  
<style >
.app {
    height: 100%;
    width: 100%;
    display: flex;
}


* {
    margin: 0;
    padding: 0;
}


#mapBox {
    height: 100%;
    width: 100%;

}

#sideBar {
    min-width: 300px;

    height: 100%;
    overflow-y: scroll;
    position: relative;
    right: 0%;
    z-index: 99999999;
    transition: 1.5s;
}

* {
    scrollbar-width: 5px !important;
    scrollbar-color: #5f5f5f #3C3D3F !important;
    scrollbar-face-color: #5c5c5c !important;
    /* Firefox 63 compatibility */
    scrollbar-track-color: #636363 !important;
}

/* Chrome, Edge, and Safari */
*::-webkit-scrollbar {
    width: 10px !important;
}

*::-webkit-scrollbar-track {
    background: #3c3d3f00 !important;
}

*::-webkit-scrollbar-thumb {
    background-color: #8d8d8d !important;
    border-radius: 15px !important;
    border: 2px solid #3c3d3f00 !important;
}

.magnitude {
    text-align: center;
    margin-bottom: 15px;
}

.infos h5 {
    padding-bottom: 5px;
}

.mag-1 {
    width: 8px;
    height: 8px;
    background-color: rgb(255, 229, 114);
    border-radius: 50%;
}

.mag-2 {
    width: 10px;
    height: 10px;
    background-color: rgb(255, 160, 72);
    border-radius: 50%;
}

.mag-3 {
    width: 18px;
    height: 18px;
    background-color: rgb(255, 108, 23);
    border-radius: 50%;
}

.mag-4,
.mag-5 {
    width: 24px;
    height: 24px;
    background-color: rgb(253, 84, 84);
    border-radius: 50%;
}

.mag-6,
.mag-7 {
    width: 32px;
    height: 32px;
    background-color: rgb(201, 0, 0);
    border-radius: 50%;
}

.magSize {
    font-size: 14px;
}

.lastLocationData {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.searchBar {
    margin: 32px 30px 23px 25px;
}

.sidebarSwitchStatus {
    margin-left: 20px;
}

.sidebarHidden {
    right: 500px !important;
    transition: 3s;
}

.leftSidebar {
    transition: 1s;
    display: flex;
    position: absolute;

}

.sidebarSwitch {

    position: absolute;
    color: #ffffff;
    margin-left: 10px;
    z-index: 9999999;
    padding: 8px;
    border-radius: 50%;
    background: #ff976a;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: rgb(255 207 166 / 55%) 0px 0px 7px 6px;
    cursor: pointer;
    height: 38px;
    margin-top: 10px;
}

.sidebarSwitch svg {
    width: 22px;
    height: 22px;
}

.searchBar input {
    width: 100%;
    background-color: transparent;
    outline: none;
    border: none;
    color: #c3c3c3;
    font-size: 16px;
    border-bottom: 1px solid #ffffff00;
    transition: .2s;
}

.searchBar input:focus {
    border-bottom: 1px solid #81a1ff;
    box-shadow: rgb(69 111 173 / 55%) 0px 6px 7px -4px;
}

.searchBar input::placeholder {
    color: #a9a9a9;
}

.lastTitle {
    padding: 3px 14px;
    border: 1px solid #a1a1a1;
    border-radius: 7px;
    box-shadow: rgb(133 133 133 / 55%) 0px 0px 12px;
}

.locationData {
    border: 1px solid rgb(204 204 204 / 11%);
    margin: 10px 25px;
    padding: 12px 19px;
    box-shadow: rgb(0 81 255 / 10%) 0px 0px 20px;
    transition: 0.3s;
    position: relative;
    z-index: 10;
    background-color: rgb(255, 255, 255);
    border-radius: 5px;
    color: #1c5f9b;
    cursor: pointer;
}

.fw-300 {
    font-weight: 300;
    font-size: 14px;
}

.headInfo {

    font-size: 13px;
    display: flex;
    justify-content: space-between;
    align-items: center;

}

.headInfo h3 {
    margin: 0px 5px;
}

.locationAddress {
    font-size: 13px;
}

.lastLocation {
    box-shadow: rgb(255 255 255 / 55%) 0px 0px 20px;
}


.leaflet-popup-content-wrapper {
    border-radius: 3px !important;
}

.leaflet-popup-tip {
    width: 12px !important;
    height: 8px !important;
    padding: 1px !important;
    margin: -6px auto 0px !important;
}

.lastEarthQuake {
    animation: pulse 2s infinite;
}

@keyframes pulse {
    0% {
        transform: scale(0.95);
        box-shadow: 0 0 0 3px rgb(255, 255, 255);
    }

    70% {
        transform: scale(1.2);
        box-shadow: 0 0 0 15px rgba(255, 255, 255, 0);
    }

    100% {
        transform: scale(0.95);
        box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
    }
}
</style>
  