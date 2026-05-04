
<script setup>
import AboutSection from '@/componnents/landingPage/AboutSection.vue';
import BenefitsSection from '@/componnents/landingPage/BenefitsSection.vue';
import CtaSection from '@/componnents/landingPage/CtaSection.vue';
import DeliverySection from '@/componnents/landingPage/DeliverySection.vue';
import FeatureSection from '@/componnents/landingPage/FeatureSection.vue';
import FooterComponent from '@/componnents/landingPage/FooterComponent.vue';
import HeroSection from '@/componnents/landingPage/HeroSection.vue';
import HowItWorksSection from '@/componnents/landingPage/HowItWorksSection.vue';
import RestaurantSection from '@/componnents/landingPage/RestaurantSection.vue';
import StatsSection from '@/componnents/landingPage/StatsSection.vue';
import TestimonialsSection from '@/componnents/landingPage/TestimonialsSection.vue';
</script>

<template>
    <main>
        <HeroSection/>
        <AboutSection/>
        <HowItWorksSection/>        
        <FeatureSection/>
        <BenefitsSection/>
        <RestaurantSection/>
        <TestimonialsSection/>
        <DeliverySection/>
        <StatsSection/>
        <CtaSection/>
        <FooterComponent />
    </main>
</template>