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
            <div class="profile-photo" style="display: flex; align-items: center;">
                <div style="margin-right: 12px; margin-left: 20px; margin-top: 3px;"><span class="text-truncate"
                        style="font-style: normal; font-weight: bold; font-size: 14px; line-height: 18px; text-align: right; display: block; color: aliceblue;">
                        Adnan Üzülmez

                    </span></div>
                <div style="margin-right: 10px;">
                    <svg xmlns="http://www.w3.org/2000/svg" width="55" height="55" fill="currentColor"
                        class="bi bi-person-circle" viewBox="0 0 16 16"
                        style="height: 55px; width: 55px; border-radius: 50%; background: rgb(141, 141, 141); color: rgb(233, 233, 233); box-shadow: rgb(255 255 255 / 24%) 0px 1px 14px; display: flex; justify-content: center; align-items: center; font-size: 55px;">
                    <path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0z" />
                    <path fill-rule="evenodd"
                        d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8zm8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1z" />
                    </svg>
                </div>
            </div>
        </div>

        <div class="content-container">
            <div class="sidebar">
                <p class="sidebar-buttons" @click="() => select = 'booking'">Rezervasyon</p>
                <p class="sidebar-buttons">Odalar</p>
                <p class="sidebar-buttons" @click="select = 'map'">Harita</p>
            </div>
            <div class="content">
                <Booking v-if="select === 'booking'"/>
                <Map v-if="select === 'map'"/>
            </div>
        </div>

    </div>
</template>

<script>
import Booking from "./Booking.vue"
import Map from "./Map.vue"
export default {
    components:{
        Booking,
        Map
    },
    data() {
        return {
            select: "booking"
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

.content{
    display: flex;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.sidebar-buttons{
    padding: 15px 0;
    color: #e7f4ff;
    text-shadow: 0 0 10px #FFFFFF;
    cursor: pointer;
}

</style>