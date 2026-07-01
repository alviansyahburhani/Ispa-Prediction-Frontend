<template>
  <section class="relative pt-20 overflow-hidden min-h-[921px] flex items-center">
    <!-- Hero Background Image -->
    <div class="absolute inset-0 z-0 overflow-hidden">
      <div ref="heroBg" class="w-full h-full bg-cover bg-center scale-110" data-alt="Medical clinic interior" style="background-image: url('https://lh3.googleusercontent.com/aida-public/AB6AXuCvN0rvua5SS9PUSQBsovnGKjqwHayVCNtLKhjbDjPCzaomGqRpKOhQkHUwKDRKhtlUYmJrg4AUgLBR3YudWGyD0bMvsOQvzA-RC750zFknoo3sw0EKMPws7KvZOkfr6A_c6AqEI-LJjRgr5wQaik3T-9fn6CMPSWlO3Sa4os0Gj4Oo7nLB58lJmgzt93LrQwtVQBOBQf46DwHWNgwK5gRTcBP0t0IQ9VVVRK15XgLWg3FMVR-vWM-JhCiJyw_5_irD5Za0Xh8gjIA')"></div>
      <div class="absolute inset-0 bg-gradient-to-r from-surface-bright via-surface-bright/90 to-transparent"></div>
    </div>
    
    <div class="relative z-10 w-full max-w-container-max mx-auto px-margin-x flex flex-col items-start gap-stack-lg">
      <div class="max-w-2xl">
        <span class="hero-item opacity-0 translate-y-4 inline-flex items-center gap-2 px-3 py-1 bg-primary-container/10 text-primary rounded-full font-label-md mb-stack-md">
          <span class="material-symbols-outlined text-[18px]">verified_user</span>
          Terpercaya & Akurat
        </span>
        <h1 class="hero-item opacity-0 translate-y-4 font-headline-lg text-headline-lg md:text-headline-lg text-primary leading-tight mb-stack-md">
          Deteksi Dini Gejala <span class="text-primary-container">ISPA Anda</span>
        </h1>
        <p class="hero-item opacity-0 translate-y-4 font-body-lg text-body-lg text-on-surface-variant mb-stack-lg leading-relaxed">
          Lindungi kesehatan keluarga Anda dengan sistem deteksi cerdas kami. Identifikasi gejala infeksi saluran pernapasan akut secara cepat, aman, dan dari kenyamanan rumah Anda.
        </p>
        <div class="hero-item opacity-0 translate-y-4 flex flex-wrap gap-gutter">
          <a class="bg-primary text-on-primary px-8 py-4 rounded-lg font-label-md text-lg hover:shadow-lg transition-all transform hover:-translate-y-0.5" href="#diagnosis-section">
            Mulai Diagnosis
          </a>
          <button class="border border-primary text-primary px-8 py-4 rounded-lg font-label-md text-lg hover:bg-primary/5 transition-all">
            Pelajari Lebih Lanjut
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';

const heroBg = ref(null);

onMounted(() => {
  gsap.to(heroBg.value, {
    scale: 1,
    duration: 1.5,
    ease: "power2.out"
  });

  gsap.to('.hero-item', {
    y: 0,
    opacity: 1,
    duration: 0.8,
    stagger: 0.2,
    ease: "power3.out",
    delay: 0.3
  });
});
</script>
