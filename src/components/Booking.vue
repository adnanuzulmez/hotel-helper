<template>
    <div class="booking">
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
               <!-- <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-5-square"
                    viewBox="0 0 16 16">
                    <path
                        d="M7.994 12.158c-1.57 0-2.654-.902-2.719-2.115h1.237c.14.72.832 1.031 1.529 1.031.791 0 1.57-.597 1.57-1.681 0-.967-.732-1.57-1.582-1.57-.767 0-1.242.45-1.435.808H5.445L5.791 4h4.705v1.103H6.875l-.193 2.343h.064c.17-.258.715-.68 1.611-.68 1.383 0 2.561.944 2.561 2.585 0 1.687-1.184 2.806-2.924 2.806Z" />
                    <path
                        d="M0 2a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V2Zm15 0a1 1 0 0 0-1-1H2a1 1 0 0 0-1 1v12a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V2Z" />
                </svg>
                <div></div>Oda No-->
            </div> 
        </div>
        <div class="booking-content">
            <div class="booking-template">
                <div class="booking-datas"  v-for="users, index in userDatas" :key="index">
                    <div class="room-window" :id="'room'+index" v-if="roomStatus == 'room'+index">
                        <div @click="closeRoomWindow('room'+index)" class="delete" style="position: absolute;top: 10px;right: 0px;">
                            <svg style="margin-right: 8px; color: #ff8181; cursor: pointer;" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                                class="bi bi-x-circle-fill" viewBox="0 0 16 16">
                                <path
                                    d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293 5.354 4.646z" />
                            </svg>
                        </div>
                        <div class="room-container">
                            <div class="rooms" v-for="rooms, index in dummyRooms" :key="index" :value="index">
                                
                            </div>
                        </div>
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
                            <div class="ok" @click="roomStatusFunc(index)">
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
export default {
    data(){
        return{
            userDatas: [],
            dummyRooms: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25],
            roomStatus: false,
        }
    },
    mounted(){

        this.getUser()

    },
    methods:{
        getUser(){
            axios.get('http://192.168.195.165:3000/users')
            .then((response) => {
                this.userDatas = response.data
                
            })
        },
        roomStatusFunc(index){
            this.roomStatus = 'room'+index
            
            console.log(this.roomStatus);
            
        },
        closeRoomWindow(index){
            console.log(index);
            console.log(document.getElementById(index));
            if(index === document.getElementById(index).getAttribute('id')){
                console.log(index);
                this.roomStatus = false
            }
        }
    }
}
</script>

<style>
.booking {
    display: flex;
    width: 100%;
    margin: 20px 20px;
    flex-direction: column;
}

.room-window{
    position: absolute;
    display: flex;
    width: 200px;
    height: 200px;
    justify-content: center;
    align-items: center;
    right: 35px;
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    background-color: #f6f6f6;
    border-radius: 6px;
    
}

.room-container{
    display: flex;
    flex-wrap: wrap;
    flex-basis: calc(100% / 2);
    align-content: center;
    justify-content: center;
    align-items: center;
    width: 200px;
    height: 200px;
}

.rooms{
    width: 10px;
    height: 10px;
    border-radius: 3px;
    margin: 0px;
    background-color: green;
    margin: 4px;
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
    font-size: 13px;
    display: flex;
    width: 130px;
}

.header-title svg {
    margin-right: 5px;
}</style>