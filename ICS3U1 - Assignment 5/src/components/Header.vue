<script setup>
    
</script>

<template>
    <header>
        <div class="logo">ChungFlix</div>
        <div class="buttons">
            <button type="button">Join Now</button>
            <button type="button">Log In</button>
        </div>
    </header>
</template>

<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif, sans-serif;
    color:white;
    background-color: black;
}

header {
    display: flex;
    align-items: center;
    padding: 20px 20px;
    background-color: black;
    color:white;
}

header .logo {
    font-size: 26px;
    font-weight: bold;
    color: red;
    letter-spacing: 1px;
}

header .buttons {
    margin-left: auto;
}

.buttons button {
    background-color: rgb(247, 247, 247);
    padding: 10px 20px;
    color: rgb(0, 0, 0); 
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    border: none;
    margin: 0px 5px;
    border-radius: 100px;
}

.buttons button:hover {
    transform: scale(1.05);
    background-color: rgb(116, 116, 116);
}

</style>