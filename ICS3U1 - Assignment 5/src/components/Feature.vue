<script setup>

</script>

<template>
    <h2>Featured Movies</h2>
        <div class="movie-grid">
            <div class="movie-card">
                <img src="../assets/moneyball.jpg">
                <p>Moneyball</p>
            </div>
            <div class="movie-card">
                <img src="../assets/transformers.jpg">
                <p>Transformers</p>
            </div>
            <div class="movie-card">
                <img src="../assets/oppenheimer.jpg">
                <p>Oppenheimer</p>
            </div>
        </div>
</template>

<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}


.movie-grid {
    display: flex;
    justify-content: center;
    gap: 30px;
}

.movie-card {
    
    padding: 10px;
    width: 320px;
}

.movie-card img {
    width: 100%;
    height: 100%;
}

#features {
    padding: 40px 20px;
    text-align:center;
    background-color: rgb(0, 0, 0);
    color:white;
}

#features h2 {
    font-size:32px;
    margin-bottom: 20px;
    
}

.movie-card:hover {
    transform: scale(1.05,1.05);
}



</style>