<script setup>
defineProps({
    pages: Array,
    handleChangePage: Function,
    activePage: Number,
})
</script>
<template>
    <div class="pagination">
        <span v-for="page in pages" @click=handleChangePage(page)
            :class="`page ${page === activePage ? 'active' : ''}`">{{ page }}</span>
    </div>
</template>
<style scoped>
.pagination {
    display: flex;
    padding: 20px;
    gap: 5px;
}

.page {
    border: 1px solid #00ff1a;
    padding: 7px;
    cursor: pointer;
    color: #ffffff;
}

.active {
    background: #4ca341;
}
</style>