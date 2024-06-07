<script setup>
import { statusesSelected } from '../constants/statusesSelected'
</script>
<template>
    <select v-model="selectedStatus" class="select">
        <option v-for="option in statusesSelected" :value='option.id'>{{ option.name }}</option>
    </select>
</template>
<style scoped>
.select {
    width: 70%;
    padding: 10px;
    font-size: 15px;
    border-radius: 10px;
    cursor: pointer;
}
</style>