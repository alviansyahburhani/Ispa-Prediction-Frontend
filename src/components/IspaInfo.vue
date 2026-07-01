<template>
  <section id="about-ispa" class="py-section-gap bg-surface" ref="infoSection">
    <div class="max-w-container-max mx-auto px-margin-x">
      <div class="text-center mb-16">
        <h2 class="font-headline-md text-headline-md text-primary mb-4">Apa itu ISPA?</h2>
        <p class="font-body-md text-body-md text-on-surface-variant max-w-2xl mx-auto">
          Infeksi Saluran Pernapasan Akut (ISPA) adalah infeksi yang menyerang saluran pernapasan, baik bagian atas maupun bawah, yang dapat timbul secara mendadak.
        </p>
      </div>
      
      <!-- Bento-style Grid for Intro Cards -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
        <!-- Card 1 -->
        <div class="info-card opacity-0 translate-y-8 card-elevation bg-surface-container-lowest p-stack-lg rounded-xl flex flex-col gap-stack-md border border-tertiary/5 hover:border-primary/20 transition-colors">
          <div class="w-12 h-12 rounded-lg bg-secondary-container flex items-center justify-center text-on-secondary-container">
            <span class="material-symbols-outlined" style="font-variation-settings: 'FILL' 1;">coronavirus</span>
          </div>
          <h3 class="font-headline-sm text-headline-sm text-on-surface">Penyebab Umum</h3>
          <p class="font-body-md text-body-md text-on-surface-variant">
            Disebabkan oleh virus atau bakteri yang menyebar melalui percikan air liur (droplet) saat penderita batuk atau bersin.
          </p>
        </div>
        
        <!-- Card 2 -->
        <div class="info-card opacity-0 translate-y-8 card-elevation bg-surface-container-lowest p-stack-lg rounded-xl flex flex-col gap-stack-md border border-tertiary/5 hover:border-primary/20 transition-colors">
          <div class="w-12 h-12 rounded-lg bg-primary-container/10 flex items-center justify-center text-primary">
            <span class="material-symbols-outlined" style="font-variation-settings: 'FILL' 1;">warning</span>
          </div>
          <h3 class="font-headline-sm text-headline-sm text-on-surface">Risiko Kesehatan</h3>
          <p class="font-body-md text-body-md text-on-surface-variant">
            Jika tidak ditangani, dapat berkembang menjadi kondisi yang lebih serius seperti pneumonia yang membutuhkan perawatan intensif.
          </p>
        </div>
        
        <!-- Card 3 -->
        <div class="info-card opacity-0 translate-y-8 card-elevation bg-surface-container-lowest p-stack-lg rounded-xl flex flex-col gap-stack-md border border-tertiary/5 hover:border-primary/20 transition-colors">
          <div class="w-12 h-12 rounded-lg bg-secondary-container flex items-center justify-center text-on-secondary-container">
            <span class="material-symbols-outlined" style="font-variation-settings: 'FILL' 1;">monitor_heart</span>
          </div>
          <h3 class="font-headline-sm text-headline-sm text-on-surface">Pentingnya Monitoring</h3>
          <p class="font-body-md text-body-md text-on-surface-variant">
            Pemantauan gejala secara mandiri membantu tenaga medis memberikan diagnosis yang lebih akurat dan tepat waktu.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
const infoSection = ref(null);

onMounted(() => {
  gsap.to('.info-card', {
    scrollTrigger: {
      trigger: infoSection.value,
      start: 'top 80%',
      toggleActions: 'play reverse play reverse'
    },
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.2,
    ease: "back.out(1.5)"
  });
});
</script>
