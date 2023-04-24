<template>
    <div class="auth-container">
        <div class="auth-form">
            <div class="auth-inputs">
                <input v-model="passwordInput" type="password">
                <p class="auth-labels">Password</p>
                <input v-model="mailInput" type="e-mail">
                <p class="auth-labels">E-mail</p>
            </div>
            <div class="sign">
                <button @click="loggedSucces()">Login</button>
            </div>
        </div>
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
                HOTEL-HELPER
            </h1>
        </div>
    </div>
</template>

<script>

export default {

    data() {
        return {
            mail: "denedene@outlook.com",
            password: "12345",
            mailInput: "",
            passwordInput: "",
            loggedStatus: false,
        }
    },
    mounted() {
        
    },
    methods: {
        loggedSucces() {
            if (this.mailInput === this.mail && this.passwordInput === this.password){
                this.loggedStatus = true
                this.$emit("loginControl", this.loggedStatus)
                console.log(this.loggedStatus);
                localStorage.setItem("logStatus", this.loggedStatus)
            }
            else{
                this.loggedStatus = false
                this.$emit("loginControl", this.loggedStatus)
                localStorage.setItem("logStatus", this.loggedStatus)
                console.log(this.loggedStatus);
            }
        }
    }
}
</script>


<style>
html,
body {
    width: 100%;
    height: 100%;
}

.auth-container {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    background-color: #7bacff;
    flex-direction: column;
}

.auth-form {
    width: 200px;
    height: 300px;
    display: flex;
    flex-direction: column;
    padding: 15px 30px;
    background-color: #ffffff;
    border-radius: 5px;
    box-shadow: #ffffff59 0px 2px 11px 2px;
}


.auth-inputs {
    display: flex;
    flex-direction: column-reverse;
}

.auth-labels {
    font-size: 12px;
    color: #566883;
    transition: .3s;
}

.auth-inputs input {
    border: none;
    height: 21px;
    font-size: 12px;
    outline: none;
    background: none;
    border-bottom: 1px solid #9e9eff;
    margin: 10px 0;
    padding: 0 8px;
    margin-bottom: 40px;
}

.auth-inputs input:focus+p {
    font-size: 17px;
}

.auth-inputs input:focus {
    border-bottom: 1px solid #80d59e;
}

.sign {
    display: flex;
    justify-content: center;
    align-items: center;
}

.sign button {
    width: 100px;
    height: 35px;
    border: none;
    border-radius: 5px;
    background: #bbf1df;
    color: #4c69f5;
    box-shadow: #5dbba559 0px 2px 11px 2px;
    cursor: pointer;
    transition: .3s;
}

.sign button:hover {
    background-color: #91d7c0;
}

.hotel-helper svg {
    filter: drop-shadow(0px 0px 8px);
    padding: 0 3px;
}

.hotel-helper h1 {
    color: #e7f4ff;
    text-shadow: 0 0 10px #FFFFFF;
}
</style>
