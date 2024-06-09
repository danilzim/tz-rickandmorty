<script setup>
defineProps({
    statusesSelected: Array,
})
</script>
<template>
    <select v-model="selectedStatus" class="select">
        <option v-for="option in statusesSelected" :value='option.id'>{{ option.name }}</option>
    </select>
</template>
<style scoped>
.select {
    width: 100%;
    padding: 10px;
    font-size: 15px;
    border-radius: 10px;
    cursor: pointer;
}

@media (max-width: 950px) {
    .select {
        height: 70%;
        padding: 5px;
        font-size: 10px;
    }
}
</style>