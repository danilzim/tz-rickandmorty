<script setup>
import CharacterCard from './CharacterCard.vue';

defineProps({
    characters: Object
})
</script>

<template>
    <div class="container">
        <CharacterCard 
        v-for="character in characters" 
        v-key="character.id" 
        :title="character.name"            
        :imageUrl="character.image" 
        :status="character.status"
        :location="character.location.name"
        :firstSeen="character.origin.name" />
    </div>
</template>

<style scoped>
.container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding-top: 20px;
    gap: 30px;
}
</style>