<template>
  <section id="alur-penggunaan" class="py-section-gap bg-surface-container-lowest" ref="alurSection">
    <div class="max-w-container-max mx-auto px-margin-x">
      <div class="text-center mb-16">
        <h2 class="font-headline-md text-headline-md text-primary mb-4">Alur Penggunaan</h2>
        <p class="font-body-md text-body-md text-on-surface-variant max-w-2xl mx-auto">
          Proses deteksi dini yang mudah, cepat, dan terpercaya dalam tiga langkah sederhana.
        </p>
      </div>
      <div class="relative">
        <!-- Connecting Line (Desktop) -->
        <div class="alur-line hidden md:block absolute top-8 left-0 w-full h-0.5 bg-primary-container/20 z-0 origin-left scale-x-0"></div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter relative z-10">
          <!-- Step 1 -->
          <div class="alur-step opacity-0 translate-y-8 flex flex-col items-center text-center gap-stack-md group">
            <div class="relative">
              <div class="w-16 h-16 rounded-full bg-primary text-on-primary flex items-center justify-center mb-2 transition-transform group-hover:scale-110 shadow-lg">
                <span class="material-symbols-outlined text-3xl">checklist</span>
              </div>
              <div class="absolute -top-2 -right-2 w-6 h-6 bg-secondary-container text-on-secondary-container rounded-full flex items-center justify-center text-xs font-bold border-2 border-surface-container-lowest">1</div>
            </div>
            <div class="flex flex-col gap-2">
              <h3 class="font-headline-sm text-headline-sm text-on-surface">Pilih Gejala</h3>
              <p class="font-body-md text-on-surface-variant px-4">Masukkan gejala yang Anda alami pada formulir diagnosis yang tersedia.</p>
            </div>
          </div>
          
          <!-- Step 2 -->
          <div class="alur-step opacity-0 translate-y-8 flex flex-col items-center text-center gap-stack-md group">
            <div class="relative">
              <div class="w-16 h-16 rounded-full bg-primary text-on-primary flex items-center justify-center mb-2 transition-transform group-hover:scale-110 shadow-lg">
                <span class="material-symbols-outlined text-3xl">psychology</span>
              </div>
              <div class="absolute -top-2 -right-2 w-6 h-6 bg-secondary-container text-on-secondary-container rounded-full flex items-center justify-center text-xs font-bold border-2 border-surface-container-lowest">2</div>
            </div>
            <div class="flex flex-col gap-2">
              <h3 class="font-headline-sm text-headline-sm text-on-surface">Analisis Sistem</h3>
              <p class="font-body-md text-on-surface-variant px-4">Sistem cerdas kami akan menganalisis data Anda secara instan menggunakan algoritma medis.</p>
            </div>
          </div>
          
          <!-- Step 3 -->
          <div class="alur-step opacity-0 translate-y-8 flex flex-col items-center text-center gap-stack-md group">
            <div class="relative">
              <div class="w-16 h-16 rounded-full bg-primary text-on-primary flex items-center justify-center mb-2 transition-transform group-hover:scale-110 shadow-lg">
                <span class="material-symbols-outlined text-3xl">assignment_turned_in</span>
              </div>
              <div class="absolute -top-2 -right-2 w-6 h-6 bg-secondary-container text-on-secondary-container rounded-full flex items-center justify-center text-xs font-bold border-2 border-surface-container-lowest">3</div>
            </div>
            <div class="flex flex-col gap-2">
              <h3 class="font-headline-sm text-headline-sm text-on-surface">Hasil Diagnosis</h3>
              <p class="font-body-md text-on-surface-variant px-4">Dapatkan hasil skrining awal dan rekomendasi langkah selanjutnya untuk kesehatan Anda.</p>
            </div>
          </div>
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
const alurSection = ref(null);

onMounted(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: alurSection.value,
      start: 'top 75%',
      toggleActions: 'play reverse play reverse'
    }
  });

  tl.to('.alur-step', {
    y: 0,
    opacity: 1,
    duration: 0.6,
    stagger: 0.2,
    ease: "power2.out"
  })
  .to('.alur-line', {
    scaleX: 1,
    duration: 0.8,
    ease: "power2.inOut"
  }, "-=0.4");
});
</script>
