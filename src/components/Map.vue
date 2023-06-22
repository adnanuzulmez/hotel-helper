<template>
  <div class="app">
    <div class="leftSidebar" :class="[sidebarFlag === 0 ? 'sidebarHidden' : '']">
      <div id="sideBar">
        <div
          class="locationData"
          v-for="(item, index) in position"
          :key="index"
          @click="setCenterByLocation(item.id, index)"
        >
          <div class="headInfo">
            <h3 class="locationNumber magSize" style="cursor: pointer">
              {{ item.popup.hotelName }}
            </h3>
            <h4>●</h4>
            <h3 class="locationNumber fw-300" style="cursor: pointer">
              Boş Oda: {{ item.popup.freeRoomCount }}
            </h3>
            <h4>●</h4>
            <h3 class="locationNumber fw-300" style="cursor: pointer">
              Dolu Oda: {{ item.popup.busyRoomCount }}
            </h3>
          </div>
          <div>
            <div class="lastLocationData">
              <p class="locationAddress" style="cursor: pointer"></p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="mapBox">
      <l-map
        :zoom="zoom"
        :center="center"
        :min-zoom="minZoom"
        :max-zoom="maxZoom"
        ref="map"
      >
        <l-tile-layer :url="mapCreator" :attribution="attribution" />
        <l-marker
          v-for="(item, index) in position"
          :key="index"
          :lat-lng="item.position"
          @click="() => (center = [item.position.lat, item.position.lng])"
        >
          <l-popup style="width: 770px;" > 
            <div class="magnitude">
              <h2 style="font-size: 20px; color: #446c8f ; display: flex; justify-content: center;">
                {{ item.popup.hotelName }}
              </h2>
            </div>
            <div class="room-window-map">
                    <select  id="hotel-select" style="top: 10px; left: 14px;" @change="userSelect($event)"> 
                        <option :value="user._id" v-for="user, index in userDatas" :key="index" >
                            {{ user.name }} {{ user.surname }}
                        </option>
                    </select>
                    <div class="able-rooms">
                        <span> Müsait Odalar</span>
                    </div>
                        
                        <div class="room-container">
                            <div class="rooms" :tabindex="index" v-for="rooms, index in roomDatas[index]" :key="index" :value="rooms.roomNo" :class="[rooms.status === true ? 'room-full' : '']" @click="getRoomValue(rooms._id, rooms.status, rooms.hotel._id)">
                                {{ rooms.roomNo }}
                            </div>
                        </div>
                        <date-picker v-model="dateAll" range valueType="format" :inline="true" ></date-picker>
                        <span class="reservation-text" @click="reservation()">REZERVASYON</span>
                    </div>
          </l-popup>
          <l-icon>
            <div :id="item.id">
              <svg
                style="
                  color: #2a79db;
                  filter: drop-shadow(0px 0px 17px);
                  background-color: white;
                "
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                fill="currentColor"
                class="bi bi-h-square-fill"
                viewBox="0 0 16 16"
              >
                <path
                  d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2Zm9 4.002V12H9.67V8.455H6.33V12H5V4.002h1.33v3.322h3.34V4.002H11Z"
                />
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
import { LMap, LTileLayer, LMarker, LIconDefault, LPopup, LIcon } from "vue2-leaflet";
import "leaflet/dist/leaflet.css";
import axios from "axios";
import DatePicker from 'vue2-datepicker';
import 'vue2-datepicker/index.css';
import { Toast } from "toaster-js";
import "toaster-js/default.css"; 
let cityId;
export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LIconDefault,
    LPopup,
    LIcon,
    DatePicker
  },
  data() {
    return {
      zoom: 4,
      minZoom: 4,
      maxZoom: 15,
      path: "/images/",
      center: [36.547591, 31.982151],
      popupOpen: "",
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      citySearch: "",
      searchArray: [],
      sidebarFlag: 1,
      mapCreator: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      position: [],
      roomDatas: [],
      hotelName: "",
      ableRooms: [],
      userDatas: [],
      dateAll: "",
      selectedCustomer: "",
      selectedRoom: "",
      selectedHotel: "",
      beginDate: "",
      endDate: "",
      roomIsAble: "",
    };
  },
  mounted() {
    this.getHotels();
    this.getRooms();
    this.getUser()
    let leafletZoom = document.querySelector(".leaflet-left");
    leafletZoom.remove();
  },

  watch: {
    dateAll(){
            console.log(this.dateAll[0]);
            this.beginDate = this.dateAll[0]
            this.endDate = this.dateAll[1]
        }
  },
  methods: {
    getUser() {
      axios.get("http://192.168.1.109:3000/users").then((response) => {
        this.userDatas = response.data;
      });
    },

    
    getHotels() {
      axios.get("http://192.168.1.109:3000/hotels").then((response) => {
        this.hotelDatas = response.data;
      });
    },

    userSelect(event) {
      this.selectedCustomer = event.target.value;
      console.log(this.selectedCustomer);
    },
    getRooms() {
      axios.get("http://192.168.1.109:3000/rooms").then((response) => {
        this.hotelDatas.map((item, index) => {
          this.hotelName = item.name;
          this.roomDatas[index] = response.data.filter(
            (item) => item.hotel.name === this.hotelName
          );
          this.ableRooms[index] = this.roomDatas[index].filter(
            (item) => item.status === false
          ).length;
        });
        this.position = [
          {
            position: { lat: 36.547591, lng: 31.982151 },
            id: 0,
            popup: {
              hotelName: this.roomDatas[0][0].hotel.name,
              freeRoomCount: this.ableRooms[0],
              busyRoomCount: 25 - this.ableRooms[0],
            },
          },
          {
            position: { lat: 36.557157, lng: 31.965767 },
            id: 1,
            popup: {
              hotelName: this.roomDatas[1][0].hotel.name,
              freeRoomCount: this.ableRooms[1],
              busyRoomCount: 25 - this.ableRooms[1],
            },
          },
          {
            position: { lat: 36.766682, lng: 31.389935 },
            id: 2,
            popup: {
              hotelName: this.roomDatas[2][0].hotel.name,
              freeRoomCount: this.ableRooms[2],
              busyRoomCount: 25 - this.ableRooms[2],
            },
          },
          {
            position: { lat: 36.820561, lng: 31.283972 },
            id: 3,
            popup: {
              hotelName: this.roomDatas[3][0].hotel.name,
              freeRoomCount: this.ableRooms[3],
              busyRoomCount: 25 - this.ableRooms[3],
            },
          },
          {
            position: { lat: 36.674043, lng: 30.555277 },
            id: 5,
            popup: {
              hotelName: this.roomDatas[4][0].hotel.name,
              freeRoomCount: this.ableRooms[4],
              busyRoomCount: 25 - this.ableRooms[4],
            },
          },
        ];
        console.log(this.ableRooms);
      });
    },

    reservation(){
            const params = {
                name: "12",
                user: this.selectedCustomer,
                room: this.selectedRoom,
                hotel: this.selectedHotel,
                checkInDate: this.beginDate,
                checkOutDate: this.endDate,
                totalAmount: "12",
            }
            if (this.selectedRoom == "" || this.selectedHotel == "" || this.beginDate == "" || this.endDate == "") {
                new Toast("Alanlar Bos Olamaz", Toast.TYPE_ERROR, Toast.TIME_LONG);
            }
            if(this.roomIsAble != true){
                axios.post('http://192.168.1.109:3000/reservations', {params})
                .then((response) => {
                this.getRooms()
                new Toast("Rezervasyon Basarili", Toast.TYPE_DONE, Toast.TIME_LONG);
            })
            
            }
            else{
                new Toast("Dolu Bir Odaya Rezervasyon Yapilamaz", Toast.TYPE_ERROR, Toast.TIME_LONG);
            }
        },
        getRoomValue(roomNo, roomStatus, index){
            this.selectedRoom = roomNo
            this.roomIsAble = roomStatus
            this.selectedHotel = index
            console.log(this.selectedRoom + `===` + this.selectedHotel);
            
        },

    setCenterByLocation(id) {
      cityId = this.position.filter((item) => item.id === id);
      setTimeout(async () => {
        await this.$refs.map.mapObject.flyTo(cityId[0].position, 13, { duration: 3.2 });
      }, 10);
      setTimeout(() => {
        this.x = document.querySelectorAll(`.leaflet-marker-icon`);
        Array.from(this.x).map((item) => {
          if (item.childNodes[0].getAttribute("id") === JSON.stringify(cityId[0].id)) {
            item.childNodes[0].click();
          }
        });
      }, 3300);
    },
  },
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

.room-window-map{
    position: relative;
    display: flex;
    width: 785px;
    height: 315px;
    justify-content: center;
    align-items: center;
    right: 9px;
    box-shadow: rgb(0 124 255 / 31%) 0px 0px 12px 0px;
    background-color: #e7edff;
    border-radius: 6px;
    top: 4px;
}
.leaflet-popup{
    width: 810px !important;
}
* {
  scrollbar-width: 5px !important;
  scrollbar-color: #5f5f5f #3c3d3f !important;
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


.leftSidebar {
  transition: 1s;
  display: flex;
  position: absolute;
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

.rooms:focus{
    box-shadow: rgba(120, 255, 105, 0.9) 0px 0px 0px 4px;
}

.rooms{
    transition: .3s;
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


</style>
