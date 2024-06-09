<script setup>
import { onMounted, ref } from 'vue';
import axios from 'axios';

import CharactersList from './components/CharactersList.vue';
import Pagination from './components/Pagination.vue';
import UInput from './components/UInput.vue';
import USelect from './components/USelect.vue';
import { statusesSelected } from './constants/statusesSelected';

const URL = ('https://rickandmortyapi.com/api/character');
const characters = ref([]);
const pages = ref('');
const filteredName = ref('');
const selectedStatus = ref('');
let activePage = 1;

const getData = async (page) => {
  try {
    let queryParams = `?page=${page}`
    if (selectedStatus.value) {
      queryParams += `&status=${selectedStatus.value}`
    }
    if (filteredName.value) {
      queryParams += `&name=${filteredName.value}`
    }
    const { data } = await axios.get(`${URL}${queryParams}`);
    characters.value = data.results;
    pages.value = data.info.pages
    activePage = page;

  } catch (err) {
    console.log(err);
  }
}

onMounted(() => {
  getData(1)
})

const fetchFilteredData = () => {
  getData(1)
}

const handleChangePage = (page) => {
  getData(page)
}
</script>

<template>
  <div class="wrapper">
    <Pagination :pages="pages" :handleChangePage="handleChangePage" :activePage="activePage" />
    <div class="filter-wrapper">
      <UInput v-model="filteredName" />
      <USelect v-model="selectedStatus" :statusesSelected="statusesSelected"/>
      <button @click="fetchFilteredData" class="button">Применить</button>
    </div>
    <CharactersList :characters="characters" />
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.filter-wrapper {
  display: flex;
  justify-content: center;
  gap: 10px;
  padding: 20px;
}

.button {
  padding: 10px;
  background: #ffffff;
  cursor: pointer;
  border-radius: 10px;
  font-size: 15px;
}

@media (max-width: 950px) {
  .filter-wrapper {
    padding: 10px;
  }

  .button {
    padding: 5px;
    font-size: 12px;
  }
}
</style>
