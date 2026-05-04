<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

    const bgImages = [
        'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1920&q=80', // Platos variados
        'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?auto=format&fit=crop&w=1920&q=80', // Pizza
        'https://images.unsplash.com/photo-1548695607-9c73430ba065?q=80&w=1025&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
        'https://images.unsplash.com/photo-1550547660-d9450f859349?auto=format&fit=crop&w=1920&q=80',  // Hamburguesa
        'https://plus.unsplash.com/premium_photo-1682088887477-4f63f185ba7e?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
        'https://images.unsplash.com/photo-1621241441637-ea2d3f59db32?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
        'https://plus.unsplash.com/premium_photo-1661589677893-6b40f2c30718?q=80&w=1632&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'

    ];

    const currentIndex = ref(0);
    let timer = null;

    onMounted(() => {
        timer = setInterval(() => {
            currentIndex.value = (currentIndex.value + 1) % bgImages.length;
        }, 5000); 
    });

    onUnmounted(() => {
        if (timer) clearInterval(timer);
    });
</script>

<template>
    <section class="hero">
        <div class="hero-bg-carousel">
            <div
                v-for="(img, index) in bgImages"
                :key="index"
                class="carousel-slide"
                :class="{ active: currentIndex === index }"
                :style="{ backgroundImage: `url(${img})` }"
            >
            </div>
            <div class="carousel-overlay"></div>
        </div>

        <div class="container">
            <div class="hero-text">
                <h1>Pide comida fácil, rápido <span>sin complicaciones</span></h1>
                <p>FoodOps conecta tus platillos favoritos con entregas rápidas y seguimiento en tiempo real.</p>
                <div class="hero-buttons">
                    <a href="#" class="btn btn-primary"><i class="fa-solid fa-rocket"></i>Ver menú</a>
                    <a href="#" class="btn btn-outline-light"><i class="fa-solid fa-mobile-screen"></i>Descargar App</a>
                </div>
            </div>
        </div>

        <div class="hero-image">
            <img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=800&q=80" alt="Hamburguesa FoodOps" onerror="this.src='https://via.placeholder.com/800x600?text=Imagen+de+Comida'">
        </div>
    </section>
</template>


<style scoped>
@import "@/assets/styles/landingPage/HeroSection.css";
</style>