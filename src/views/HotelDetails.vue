<template>
    <!-- v-if="selectedHotel" -->
    <div class="fade-in-down">
        <div class="details">
            <div class="leftSide">
                <div class="image">{{ $route.params.id }}</div>
               
            </div>
            <div>
                <h2></h2>
                <p></p>
                <span></span>
            </div>
        </div>
    </div>
    </template>
    
    <script setup>
        import { useRoute } from 'vue-router';
        import store from "@/store/store";
        import {  ref , computed} from "vue";
        const hotels = computed(()=> store.getters.getHotels);
        const route = useRoute();
        const id = route.params.id;
        const hotel = hotels.value.find(hotel => hotel.id === parseInt(id));
   
    </script>
    
    <style scoped>

    </style>