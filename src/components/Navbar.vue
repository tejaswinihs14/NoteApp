<template>
    <div class="Navbar">
        <div class="navbar-logo">Notes App</div>
        <input class="searc-bar" type="search" placeholder="search"/>
        <div class="create-btn" @click="openModal"><span>📋</span></div>
        <div class="customselect-btn"> ⇅ </div>
        <div class="logout-btn"> 👋 </div>
    </div>
</template>

<script>
    export default {
        name:"Navbar",
        methods:{
            openModal(){
                this.$emit('openModal')
            }
        }
    }
</script>

<style lang='scss' scoped>

.Navbar{
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 10px 0px;
    width: 100%;
    position: fixed;
    background-color: #111;
    align-items: center;
    margin: 0px;

    .navbar-logo{
        font-size: 1.6em;
        cursor: pointer;
        color: #00a3a3;
        font-family: RocknRoll One,sans-serif;
    }

    .searc-bar{
        width: 25%;
        padding: 10px 0px;
        border: 3px solid #c4cdd1;
        outline: none;
        border-radius: 10px;
        color: #000;
        font-size: 1em;
        font-weight: 500;
        background-color: #c4cdd1;
        text-align: center;
    }

    .create-btn{
        padding: 5px;
        border-radius: 25px;
        color: #000;
        background-color: #0ff;
        font-size: 1.6em;
        font-weight: 500;
        display: flex;
        align-items: center;
        justify-content: center;

        &:hover{
            cursor: pointer;
            background-color: #00a3a3;
            box-shadow: 1px 1px 10px #00a3a3;
        }
    }

    .customselect-btn{
        border-radius: 25px;
        color: #000;
        background-color: #0ff;
        font-size: 1.6em;
        font-weight: 500;
        display: flex;
        align-items: center;
        padding: 5px;
        justify-content: center;

            &:hover{
                cursor: pointer;
                background-color: #00a3a3;
                box-shadow: 1px 1px 10px #00a3a3;
            }
    }

    .logout-btn{
        border-radius: 25px;
        color: #000;
        background-color: #0ff;
        font-size: 1.6em;
        font-weight: 500;
        display: flex;
        align-items: center;
        padding: 5px;
        justify-content: center;

            &:hover{
                cursor: pointer;
                background-color: #00a3a3;
                box-shadow: 1px 1px 10px #00a3a3;
            }
    }
}
</style>