<script setup>
defineProps({
    imageUrl: String,
    title: String,
    status: String,
    location: String,
    firstSeen: String,
})
</script>

<template>
    <div class="card">
        <img :src="imageUrl" alt="Character" class="card-img" />
        <div class="card-content">
            <div class="content-block">
                <h1 class="title">{{ title }}</h1>
                <p class="status">{{ status }}</p>
            </div>
            <div class="content-block">
                <div class="text-info">Last known location:</div>
                <p class="location">{{ location }}</p>
            </div>
            <div class="content-block">
                <div class="text-info">First seen in:</div>
                <p class="location">{{ firstSeen }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    background: #74749369;
    border-radius: 20px;
    width: 40%;
}

.title {
    font-size: 30px;
    font-weight: 900;
    color: #ffffff;
}

.status {
    font-size: 20px;
    font-weight: bold;
    color: #ffffff;
}

.text-info {
    font-size: 20px;
    color: #889d9e
}

.card-img {
    width: 45%;
    border-top-left-radius: 20px;
    border-bottom-left-radius: 20px;
}

.card-content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 20px 20px 25px 10px;
}

.location {
    font-size: 23px;
    color: #ffffff;
}
</style>