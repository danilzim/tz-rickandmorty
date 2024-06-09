<script setup></script>
<template>
    <input v-model="filteredName" class="input" placeholder="Введите имя персонажа" type="text" />
</template>
<style scoped>
.input {
    width: 100%;
    padding: 10px;
    border-radius: 10px;
    font-size: 15px;
}

@media (max-width: 950px) {
.input {
    height: 70%;
    padding: 5px;
    font-size: 10px;
}
}
</style>