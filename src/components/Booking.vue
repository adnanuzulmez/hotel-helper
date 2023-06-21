<template>
    <div class="booking">
    <h3 class="titles">
        <svg style="margin-right: 10px;" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-person"
                    viewBox="0 0 16 16">
                    <path
                        d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6Zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0Zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4Zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10Z" />
                </svg>
                Kayıt
    </h3>
        <div class="header">
            <div class="header-title"><i class="bi bi-person"></i>
                Id
            </div>
            <div class="header-title">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-person"
                    viewBox="0 0 16 16">
                    <path
                        d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6Zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0Zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4Zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10Z" />
                </svg>
                <div>İsim</div>
            </div>
            <div class="header-title">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-person"
                    viewBox="0 0 16 16">
                    <path
                        d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6Zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0Zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4Zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10Z" />
                </svg>
                <div>Soyisim</div>
            </div>
            <div class="header-title"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                    class="bi bi-card-checklist" viewBox="0 0 16 16">
                    <path
                        d="M14.5 3a.5.5 0 0 1 .5.5v9a.5.5 0 0 1-.5.5h-13a.5.5 0 0 1-.5-.5v-9a.5.5 0 0 1 .5-.5h13zm-13-1A1.5 1.5 0 0 0 0 3.5v9A1.5 1.5 0 0 0 1.5 14h13a1.5 1.5 0 0 0 1.5-1.5v-9A1.5 1.5 0 0 0 14.5 2h-13z" />
                    <path
                        d="M7 5.5a.5.5 0 0 1 .5-.5h5a.5.5 0 0 1 0 1h-5a.5.5 0 0 1-.5-.5zm-1.496-.854a.5.5 0 0 1 0 .708l-1.5 1.5a.5.5 0 0 1-.708 0l-.5-.5a.5.5 0 1 1 .708-.708l.146.147 1.146-1.147a.5.5 0 0 1 .708 0zM7 9.5a.5.5 0 0 1 .5-.5h5a.5.5 0 0 1 0 1h-5a.5.5 0 0 1-.5-.5zm-1.496-.854a.5.5 0 0 1 0 .708l-1.5 1.5a.5.5 0 0 1-.708 0l-.5-.5a.5.5 0 0 1 .708-.708l.146.147 1.146-1.147a.5.5 0 0 1 .708 0z" />
                </svg>
                <div>Kimlik Numarası</div>
            </div>
            <div class="header-title">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                    class="bi bi-calendar-date" viewBox="0 0 16 16">
                    <path
                        d="M6.445 11.688V6.354h-.633A12.6 12.6 0 0 0 4.5 7.16v.695c.375-.257.969-.62 1.258-.777h.012v4.61h.675zm1.188-1.305c.047.64.594 1.406 1.703 1.406 1.258 0 2-1.066 2-2.871 0-1.934-.781-2.668-1.953-2.668-.926 0-1.797.672-1.797 1.809 0 1.16.824 1.77 1.676 1.77.746 0 1.23-.376 1.383-.79h.027c-.004 1.316-.461 2.164-1.305 2.164-.664 0-1.008-.45-1.05-.82h-.684zm2.953-2.317c0 .696-.559 1.18-1.184 1.18-.601 0-1.144-.383-1.144-1.2 0-.823.582-1.21 1.168-1.21.633 0 1.16.398 1.16 1.23z" />
                    <path
                        d="M3.5 0a.5.5 0 0 1 .5.5V1h8V.5a.5.5 0 0 1 1 0V1h1a2 2 0 0 1 2 2v11a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V3a2 2 0 0 1 2-2h1V.5a.5.5 0 0 1 .5-.5zM1 4v10a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V4H1z" />
                </svg>
                <div></div>Doğum Tarihi
            </div>
             <div class="header-title">
              
            </div> 
        </div>
        <div class="booking-content">
            <div class="booking-template">
                <div class="booking-datas"  v-for="users, index in userDatas" :key="index">
                    <div class="room-window" :id="'room'+index" v-if="roomStatus == 'room'+index">
                    <select  id="hotel-select" @change="hotelSelect($event)"> 
                        <option :value="hotel._id" v-for="hotel, index in hotelDatas" :key="index" >
                            {{ hotel.name }}
                        </option>
                    </select>
                    <div class="able-rooms">
                        <span> Müsait Odalar</span>
                    </div>
                        <div @click="closeRoomWindow('room'+index)" class="delete" style="position: absolute;top: 10px;right: 0px;">
                            <svg style="margin-right: 8px; color: #ff8181; cursor: pointer;" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                                class="bi bi-x-circle-fill" viewBox="0 0 16 16">
                                <path
                                    d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293 5.354 4.646z" />
                            </svg>
                        </div>
                        <div class="room-container">
                            <div class="rooms" v-for="rooms, index in roomDatas" :key="index" :value="rooms.roomNo" :class="[rooms.status === true ? 'room-full' : '']" @click="getRoomValue(rooms._id, rooms.status)">
                                {{ rooms.roomNo }}
                            </div>
                        </div>
                        <date-picker v-model="dateAll" range valueType="format" :inline="true" ></date-picker>
                        <span class="reservation-text" @click="reservation()">REZERVASYON</span>
                    </div>
                    <div class="header-title">
                        {{ users._id.substring(users._id.length - 3, users._id.length) }}
                    </div>
                    <div class="header-title">
                        {{ users.name }}
                    </div>
                    <div class="header-title">
                        {{ users.surname }}
                    </div>
                    <div class="header-title">
                        {{ users.identifyNumber }}
                    </div>
                    <div class="header-title">

                        {{ users.birthDate }}
                    </div>
                    <div class="header-title" style="justify-content: space-between;">
                        
                        <div class="buttons" style="margin-right: 10px; display: flex;">
                            <div class="ok" @click="roomStatusFunc(index, users._id)">
                                <svg style="margin-right: 8px; color: #4cc923; cursor: pointer;" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                                    class="bi bi-check-square-fill" viewBox="0 0 16 16">
                                    <path
                                        d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2zm10.03 4.97a.75.75 0 0 1 .011 1.05l-3.992 4.99a.75.75 0 0 1-1.08.02L4.324 8.384a.75.75 0 1 1 1.06-1.06l2.094 2.093 3.473-4.425a.75.75 0 0 1 1.08-.022z" />
                                </svg>
                            </div>
                            <div class="delete">
                                <svg style="margin-right: 8px; color: #ff8181; cursor: pointer;" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                                    class="bi bi-x-circle-fill" viewBox="0 0 16 16">
                                    <path
                                        d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293 5.354 4.646z" />
                                </svg>
                            </div>
                            
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>

import axios from "axios"
import DatePicker from 'vue2-datepicker';
import 'vue2-datepicker/index.css';
import { Toast } from "toaster-js";
import "toaster-js/default.css"; 
export default {
    components:{
        DatePicker,
        
    },
    data(){
        return{
            userDatas: [],
            roomStatus: false,
            hotelDatas: [],
            dateAll: "",
            beginDate: "",
            endDate: "",
            selectedHotel: "648f404290ee9ff666f50c6b",
            selectedCustomer: "",
            selectedRoom: "",
            roomDatas: [],
            roomIsAble: false,
        }
    },
    mounted(){

        this.getUser()
        this.getHotels()
        this.getRooms()
    },
    watch:{
        selectedHotel(){
            
            this.getRooms()
        },
        dateAll(){
            console.log(this.dateAll[0]);
            this.beginDate = this.dateAll[0]
            this.endDate = this.dateAll[1]
        }
    },
    methods:{
        getUser(){
            axios.get('http://192.168.1.109:3000/users')
            .then((response) => {
                this.userDatas = response.data
                
            })
        },
        getHotels(){
            axios.get('http://192.168.1.109:3000/hotels')
            .then((response) => {
                this.hotelDatas = response.data
                
            })
        },
        roomStatusFunc(index, id){
            this.roomStatus = 'room'+index
            this.selectedCustomer = id
            console.log(this.selectedCustomer);
        },

        hotelSelect(event){
            this.selectedHotel = event.target.value
        },
        getRooms(){
            const params = {
                id: this.selectedHotel
            }
            axios.post('http://192.168.1.109:3000/rooms', {params})
            .then((response) => {
                this.roomDatas = response.data
            })
        },

        closeRoomWindow(index){
            console.log(index);
            console.log(document.getElementById(index));
            if(index === document.getElementById(index).getAttribute('id')){
                console.log(index);
                this.roomStatus = false
            }
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
        getRoomValue(roomNo, roomStatus){
            this.selectedRoom = roomNo
            this.roomIsAble = roomStatus
            console.log(this.selectedRoom);
        }
    }
}
</script>

<style>
@import "toastr";
.booking {
    display: flex;
    width: 100%;
    margin: 20px 20px;
    flex-direction: column;
}

.toast{
    background-color: transparent !important;
    transition: 1s;
}

.able-rooms{
    position: absolute;
    left: 85px;
    top: 60px;
    font-size: 16px;
    font-weight: 600;
    color: #838383;
}

#hotel-select{
    position: absolute;
    top: 25px;
    left: 81px;
    border-radius: 6px;
    outline: none;
    border: 1px solid #cdcdcd;
    font-size: 14px;
}

.room-full{
    background-color: #ff7171 !important;
}

.reservation-text{
    position: absolute;
    left: 52px;
    top: 82%;
    font-weight: 800;
    font-size: 20px;
    color: #276faf;
    filter: drop-shadow(0px 0px 23px #276faf);
    border: 1px solid #8caecd;
    border-radius: 6px;
    padding: 5px 10px;
    cursor: pointer;
    transition: .3s;
}

.reservation-text:hover{
    color: #dfecff;
    background-color: #6599c7;
    
}

.room-window{
    position: absolute;
    display: flex;
    width: 785px;
    height: 315px;
    justify-content: center;
    align-items: center;
    right: 35px;
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    background-color: #f6f6f6;
    border-radius: 6px;
    
}

.mx-datepicker-inline {
    width: auto;
    margin-top: 30px;
    margin-right: 15px;
}

.room-container{
    display: flex;
    flex-wrap: wrap;
    flex-basis: calc(100% / 1.0);
    align-content: end;
    justify-content: center;
    align-items: end;
    margin-bottom: 35px;
    width: 200px;
    height: 200px;
    
}

.rooms{
    width: 42px;
    height: 20px;
    border-radius: 2px;
    margin: 0px;
    background-color: #4fa14f;
    margin: 4px;
    color: white;
    font-size: 13px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer ;
}

.header {
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding: 10px 0;
    margin: 10px 0;
    background-color: #dce6ef;
    border-radius: 5px;
    box-shadow: rgb(84 136 255 / 24%) 0px 1px 14px;
}

.booking-datas {
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding: 5px 0;
    margin: 15px 0;
    background-color: #e7e7e7;
    border-radius: 5px;
    box-shadow: rgb(119 127 145 / 24%) 0px 1px 14px;
}

.header-title {
    padding: 0 15px;
    color: #386a95;
    font-size: 15px;
    display: flex;
    width: 130px;
    align-items: center;
}

.header-title svg {
    margin-right: 5px;
}</style>