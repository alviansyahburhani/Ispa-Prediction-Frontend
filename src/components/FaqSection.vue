<template>
  <section id="faq" class="py-section-gap bg-surface-container-lowest overflow-hidden" ref="faqSection">
    <div class="max-w-3xl mx-auto px-margin-x">
      <div class="text-center mb-10 faq-header opacity-0 translate-y-4">
        <h2 class="font-headline-md text-headline-md text-primary mb-4">Pertanyaan yang Sering Diajukan</h2>
      </div>
      <div class="space-y-4">
        <details class="faq-item opacity-0 translate-y-4 group bg-surface rounded-xl border border-outline-variant/50 p-4 open:shadow-md transition-all cursor-pointer">
          <summary class="font-label-md text-on-surface text-lg font-semibold list-none flex justify-between items-center outline-none">
            Apakah hasil prediksi ini 100% akurat?
            <span class="material-symbols-outlined transition-transform group-open:rotate-180 text-primary">expand_more</span>
          </summary>
          <p class="font-body-md text-on-surface-variant mt-4 pt-4 border-t border-outline-variant/20">
            Sistem ini menggunakan algoritma Machine Learning yang dilatih dengan data historis medis. Tingkat akurasinya sangat tinggi berdasarkan pengujian, namun <strong>tidak dapat dijadikan sebagai diagnosis pasti</strong>. Ini adalah alat bantu untuk skrining awal.
          </p>
        </details>
        <details class="faq-item opacity-0 translate-y-4 group bg-surface rounded-xl border border-outline-variant/50 p-4 open:shadow-md transition-all cursor-pointer">
          <summary class="font-label-md text-on-surface text-lg font-semibold list-none flex justify-between items-center outline-none">
            Apakah data kesehatan yang saya masukkan aman?
            <span class="material-symbols-outlined transition-transform group-open:rotate-180 text-primary">expand_more</span>
          </summary>
          <p class="font-body-md text-on-surface-variant mt-4 pt-4 border-t border-outline-variant/20">
            Sangat aman. Sistem kami hanya memproses data secara real-time untuk menghasilkan prediksi. Kami tidak menyimpan data pribadi Anda di dalam server untuk melindungi privasi sesuai standar rekam medis elektronik.
          </p>
        </details>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
const faqSection = ref(null);

onMounted(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: faqSection.value,
      start: 'top 80%',
      toggleActions: 'play reverse play reverse'
    }
  });

  tl.to('.faq-header', {
    y: 0,
    opacity: 1,
    duration: 0.5,
    ease: "power2.out"
  })
  .to('.faq-item', {
    y: 0,
    opacity: 1,
    duration: 0.5,
    stagger: 0.15,
    ease: "power2.out"
  }, "-=0.2");
});
</script>
