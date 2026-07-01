<template>
  <div class="min-h-screen bg-background font-body-md text-on-background flex flex-col selection:bg-primary-container selection:text-on-primary-container">
    <TheNavbar />
    <main class="flex-grow">
      <HeroSection />
      <IspaInfo />
      <PencegahanSection />
      <AlurPenggunaan />
      <DiagnosisForm id="diagnosis-section" />
      <RedFlags />
      <FaqSection />
    </main>
    <TheFooter />
  </div>
</template>

<script setup>
import TheNavbar from './components/TheNavbar.vue';
import HeroSection from './components/HeroSection.vue';
import IspaInfo from './components/IspaInfo.vue';
import AlurPenggunaan from './components/AlurPenggunaan.vue';
import DiagnosisForm from './components/DiagnosisForm.vue';
import RedFlags from './components/RedFlags.vue';
import PencegahanSection from './components/PencegahanSection.vue';
import FaqSection from './components/FaqSection.vue';
import TheFooter from './components/TheFooter.vue';
</script>