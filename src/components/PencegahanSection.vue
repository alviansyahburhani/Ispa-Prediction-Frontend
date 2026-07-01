<template>
  <section class="py-section-gap bg-surface overflow-hidden" ref="pencegahanSection">
    <div class="max-w-container-max mx-auto px-margin-x grid grid-cols-1 md:grid-cols-2 gap-section-gap">
      
      <!-- Edukasi Pencegahan -->
      <div class="pencegahan-content opacity-0 -translate-x-8">
        <h2 class="font-headline-md text-headline-md text-primary mb-6">Langkah Pencegahan ISPA</h2>
        <div class="space-y-4">
          <div class="flex items-start gap-4">
            <div class="w-10 h-10 rounded-lg bg-primary-container/10 flex items-center justify-center text-primary shrink-0">
              <span class="material-symbols-outlined">wash</span>
            </div>
            <div>
              <h4 class="font-label-md text-on-surface text-lg">Cuci Tangan Rutin</h4>
              <p class="font-body-md text-on-surface-variant text-sm">Gunakan sabun dan air mengalir selama minimal 20 detik, terutama setelah dari tempat umum.</p>
            </div>
          </div>
          <div class="flex items-start gap-4">
            <div class="w-10 h-10 rounded-lg bg-primary-container/10 flex items-center justify-center text-primary shrink-0">
              <span class="material-symbols-outlined">masks</span>
            </div>
            <div>
              <h4 class="font-label-md text-on-surface text-lg">Gunakan Masker</h4>
              <p class="font-body-md text-on-surface-variant text-sm">Pakai masker saat Anda sedang batuk/pilek atau ketika berada di kerumunan yang padat.</p>
            </div>
          </div>
          <div class="flex items-start gap-4">
            <div class="w-10 h-10 rounded-lg bg-primary-container/10 flex items-center justify-center text-primary shrink-0">
              <span class="material-symbols-outlined">restaurant</span>
            </div>
            <div>
              <h4 class="font-label-md text-on-surface text-lg">Jaga Imunitas Tubuh</h4>
              <p class="font-body-md text-on-surface-variant text-sm">Konsumsi makanan bergizi seimbang, perbanyak minum air putih, dan istirahat yang cukup.</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Kelompok Rentan -->
      <div class="rentan-card opacity-0 translate-x-8 card-elevation bg-surface-container-low p-stack-lg rounded-2xl border border-outline-variant/30">
        <h2 class="font-headline-sm text-headline-sm text-primary mb-4">Perhatian Ekstra (Kelompok Rentan)</h2>
        <p class="font-body-md text-on-surface-variant mb-6">
          ISPA dapat menyerang siapa saja, namun dampaknya bisa jauh lebih fatal dan membutuhkan penanganan medis segera jika terjadi pada kelompok berikut:
        </p>
        <ul class="space-y-3 font-body-md text-on-surface">
          <li class="flex items-center gap-3">
            <span class="material-symbols-outlined text-secondary">check_circle</span>
            Balita dan anak-anak.
          </li>
          <li class="flex items-center gap-3">
            <span class="material-symbols-outlined text-secondary">check_circle</span>
            Lansia (berusia di atas 60 tahun).
          </li>
          <li class="flex items-center gap-3">
            <span class="material-symbols-outlined text-secondary">check_circle</span>
            Ibu hamil.
          </li>
          <li class="flex items-center gap-3">
            <span class="material-symbols-outlined text-secondary">check_circle</span>
            Individu dengan riwayat penyakit penyerta (Asma, Diabetes, dll).
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
const pencegahanSection = ref(null);

onMounted(() => {
  gsap.to('.pencegahan-content', {
    scrollTrigger: {
      trigger: pencegahanSection.value,
      start: 'top 80%',
      toggleActions: 'play reverse play reverse'
    },
    x: 0,
    opacity: 1,
    duration: 0.8,
    ease: "power2.out"
  });

  gsap.to('.rentan-card', {
    scrollTrigger: {
      trigger: pencegahanSection.value,
      start: 'top 80%',
      toggleActions: 'play reverse play reverse'
    },
    x: 0,
    opacity: 1,
    duration: 0.8,
    delay: 0.2,
    ease: "power2.out"
  });
});
</script>
