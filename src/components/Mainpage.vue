<template>
    <div class="mainpage">
        <div class="topbar">
            <div class="hotel-helper">
                <h1>
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                        class="bi bi-h-square-fill" viewBox="0 0 16 16">
                        <path
                            d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2Zm9 4.002V12H9.67V8.455H6.33V12H5V4.002h1.33v3.322h3.34V4.002H11Z" />
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor"
                        class="bi bi-h-square-fill" viewBox="0 0 16 16">
                        <path
                            d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2Zm9 4.002V12H9.67V8.455H6.33V12H5V4.002h1.33v3.322h3.34V4.002H11Z" />
                    </svg>
                    HOTEL HELPER
                </h1>
            </div>
            <div id="profile-photo" @mouseleave="showSettings()">
                <div style="margin-right: 12px; margin-left: 20px; margin-top: 3px;"><span class="text-truncate"
                        style="font-style: normal; font-weight: bold; font-size: 14px; line-height: 18px; text-align: right; display: block; color: aliceblue;">
                        Adnan Üzülmez
                    </span>
                </div>
                <div style="margin-right: 10px;">
                    <svg xmlns="http://www.w3.org/2000/svg" width="55" height="55" fill="currentColor"
                        class="bi bi-person-circle" viewBox="0 0 16 16"
                        style="height: 55px; width: 55px; border-radius: 50%; background: rgb(141, 141, 141); color: rgb(233, 233, 233); box-shadow: rgb(255 255 255 / 24%) 0px 1px 14px; display: flex; justify-content: center; align-items: center; font-size: 55px;">
                        <path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0z" />
                        <path fill-rule="evenodd"
                            d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8zm8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1z" />
                    </svg>
                </div>
                <svg class="log-out" fill="#ff9999" height="200px" width="200px" version="1.1" id="Capa_1"
                    xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                    viewBox="-19.87 -19.87 238.46 238.46" xml:space="preserve" stroke="#ff9999" stroke-width="0.00198715" @click="logOut()">
                    <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                    <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round" stroke="#ffe5e5"
                        stroke-width="3.17944"></g>
                    <g id="SVGRepo_iconCarrier">
                        <g>
                            <path
                                d="M161.463,48.763c-2.929-2.929-7.677-2.929-10.607,0c-2.929,2.929-2.929,7.677,0,10.606 c13.763,13.763,21.342,32.062,21.342,51.526c0,19.463-7.579,37.761-21.342,51.523c-14.203,14.204-32.857,21.305-51.516,21.303 c-18.659-0.001-37.322-7.104-51.527-21.309c-28.405-28.405-28.402-74.625,0.005-103.032c2.929-2.929,2.929-7.678,0-10.606 c-2.929-2.929-7.677-2.929-10.607,0C2.956,83.029,2.953,138.766,37.206,173.019c17.132,17.132,39.632,25.697,62.135,25.696 c22.497-0.001,44.997-8.564,62.123-25.69c16.595-16.594,25.734-38.659,25.734-62.129C187.199,87.425,178.059,65.359,161.463,48.763 z">
                            </path>
                            <path
                                d="M99.332,97.164c4.143,0,7.5-3.358,7.5-7.5V7.5c0-4.142-3.357-7.5-7.5-7.5s-7.5,3.358-7.5,7.5v82.164 C91.832,93.807,95.189,97.164,99.332,97.164z">
                            </path>
                        </g>
                    </g>
                </svg>
            </div>
        </div>

        <div class="content-container">
            <div class="sidebar">
                <p class="sidebar-buttons" @click="() => select = 'booking'">Rezervasyon</p>
                <p class="sidebar-buttons">Odalar</p>
                <p class="sidebar-buttons" @click="select = 'map'">Harita</p>
            </div>
            <div class="content">
                <Booking v-if="select === 'booking'" />
                <Map v-if="select === 'map'" />
            </div>
        </div>

    </div>
</template>

<script>
import Booking from "./Booking.vue"
import Map from "./Map.vue"
export default {
    components: {
        Booking,
        Map
    },
    data() {
        return {
            select: "booking"
        }
    },
    methods: {

        logOut() {
           localStorage.removeItem("logStatus")
           location.reload();
        }

    }
}
</script>

<style>
.mainpage {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
}

.content-container {
    width: 100%;
    height: 100%;
    display: flex;
}

.topbar {
    display: flex;
    height: 80px;
    background-color: #4b638b;
    align-items: center;
    padding: 0 17px;
    justify-content: space-between;
}

.sidebar {
    height: 100%;
    min-width: 183px;
    background-color: #4b638b;
    display: flex;
    flex-direction: column;
    padding: 0 17px
}

.content {
    display: flex;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.sidebar-buttons {
    padding: 15px 0;
    color: #e7f4ff;
    text-shadow: 0 0 10px #FFFFFF;
    cursor: pointer;
}

.show-setting {
    display: flex;
}

.log-out{
    width: 30px;
    height: 30px;
    filter: drop-shadow(0px 1px 4px rgb(255, 153, 153));
}

#profile-photo {
    display: flex;
    align-items: center;
    cursor: pointer;
}</style>