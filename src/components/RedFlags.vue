<template>
  <section class="py-12 bg-error-container text-on-error-container overflow-hidden" ref="redFlagsSection">
    <div class="max-w-container-max mx-auto px-margin-x flex flex-col md:flex-row items-center gap-stack-lg">
      <div class="redflag-icon scale-0 w-16 h-16 rounded-full bg-error text-on-error flex items-center justify-center shrink-0 shadow-lg">
        <span class="material-symbols-outlined text-4xl">emergency</span>
      </div>
      <div class="redflag-text opacity-0 translate-x-8">
        <h2 class="font-headline-sm text-headline-sm font-bold mb-2 text-error">Kapan Harus Segera ke Dokter?</h2>
        <p class="font-body-md text-on-error-container/90">
          Sistem ini hanya untuk skrining awal. <strong>Segera kunjungi IGD atau fasilitas kesehatan terdekat</strong> jika Anda atau keluarga mengalami: Sesak napas berat, tarikan dinding dada ke dalam, bibir/wajah kebiruan, atau demam tinggi yang tidak turun lebih dari 3 hari.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
const redFlagsSection = ref(null);

onMounted(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: redFlagsSection.value,
      start: 'top 85%',
      toggleActions: 'play reverse play reverse'
    }
  });

  tl.to('.redflag-icon', {
    scale: 1,
    duration: 0.6,
    ease: "back.out(2)"
  })
  .to('.redflag-text', {
    x: 0,
    opacity: 1,
    duration: 0.6,
    ease: "power2.out"
  }, "-=0.4");
});
</script>
