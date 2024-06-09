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
    justify-content: center;
    padding: 20px;
    gap: 5px;
}

.page {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 30px;
    height: 30px;
    border: 1px solid #00ff1a;
    cursor: pointer;
    color: #ffffff;
}

.active {
    background: #4ca341;
}

@media (max-width: 1470px) {
    .pagination {
        flex-wrap: wrap;
    }
}

@media (max-width: 950px) {
    .page {
        width: 20px;
        height: 20px;
    }
}
</style>