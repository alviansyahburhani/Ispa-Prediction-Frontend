<template>
  <section class="py-section-gap bg-surface-container-low relative" id="diagnosis-section" ref="formSection">
    <div class="max-w-4xl mx-auto px-margin-x">
      <div class="diagnosis-card opacity-0 translate-y-12 card-elevation bg-surface-container-lowest rounded-3xl overflow-hidden flex flex-col md:flex-row shadow-xl">
        <!-- Form Sidebar Decor -->
        <div class="md:w-1/3 bg-primary p-stack-lg text-on-primary flex flex-col justify-between relative overflow-hidden">
          <div class="relative z-10">
            <h2 class="font-headline-md text-headline-md mb-stack-md">Diagnosis Gejala</h2>
            <p class="font-body-md opacity-90">Selesaikan formulir ini untuk mendapatkan evaluasi awal kondisi pernapasan Anda.</p>
          </div>
          <div class="relative z-10 mt-stack-lg">
            <div class="flex items-center gap-2 mb-2">
              <span class="material-symbols-outlined text-[20px]">timer</span>
              <span class="text-sm">Hanya butuh 2 menit</span>
            </div>
            <div class="flex items-center gap-2">
              <span class="material-symbols-outlined text-[20px]">lock</span>
              <span class="text-sm">Privasi terjaga</span>
            </div>
          </div>
        </div>
        
        <!-- Actual Form -->
        <div class="md:w-2/3 p-stack-lg md:p-12">
          <form class="space-y-stack-lg" @submit.prevent="submitDiagnosis">
            <div>
              <div class="mb-stack-lg space-y-stack-md">
                <h3 class="font-headline-sm text-on-surface mb-2">Informasi Pribadi</h3>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-stack-md">
                  <div>
                    <label class="block text-sm font-label-md text-on-surface-variant mb-1">Jenis Kelamin (JK)</label>
                    <select v-model="formData.JenisKelamin" required class="w-full p-3 rounded-lg border border-outline-variant bg-surface-container-lowest text-on-surface focus:border-primary outline-none">
                      <option value="" disabled>Pilih JK</option>
                      <option value="L">Laki-laki</option>
                      <option value="P">Perempuan</option>
                    </select>
                  </div>
                  <div>
                    <label class="block text-sm font-label-md text-on-surface-variant mb-1">Umur (Umr)</label>
                    <input v-model="formData.Umur" required class="w-full p-3 rounded-lg border border-outline-variant bg-surface-container-lowest text-on-surface focus:border-primary outline-none" placeholder="Contoh: 25" type="number"/>
                  </div>
                  <div>
                    <label class="block text-sm font-label-md text-on-surface-variant mb-1">Alamat (Almt)</label>
                    <input v-model="formData.Alamat" required class="w-full p-3 rounded-lg border border-outline-variant bg-surface-container-lowest text-on-surface focus:border-primary outline-none" placeholder="Alamat lengkap" type="text"/>
                  </div>
                </div>
                <label class="block text-primary font-label-md mt-stack-lg">Pilih semua gejala yang Anda rasakan:</label>
              </div>
              
              <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3">
                <div v-for="gejala in gejalaList" :key="gejala.key" class="flex flex-col gap-2 p-3 rounded-xl border border-outline-variant bg-surface-container-lowest">
                  <span class="text-label-md text-on-surface">{{ gejala.label }}</span>
                  <div class="flex gap-2">
                    <button 
                      type="button" 
                      @click="formData.gejala[gejala.key] = 1"
                      :class="[
                        'flex-1 py-1.5 rounded-lg border text-xs font-label-md transition-all',
                        formData.gejala[gejala.key] === 1 
                          ? 'border-primary bg-primary text-on-primary' 
                          : 'border-outline-variant text-on-surface-variant hover:bg-surface-container-high'
                      ]">Ya</button>
                    <button 
                      type="button" 
                      @click="formData.gejala[gejala.key] = 0"
                      :class="[
                        'flex-1 py-1.5 rounded-lg border text-xs font-label-md transition-all',
                        formData.gejala[gejala.key] === 0 
                          ? 'border-primary bg-primary text-on-primary' 
                          : 'border-outline-variant text-on-surface-variant hover:bg-surface-container-high'
                      ]">Tidak</button>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="pt-stack-md">
              <button class="w-full bg-primary text-on-primary py-4 rounded-lg font-headline-sm hover:bg-primary-container transition-all active:scale-[0.98] flex items-center justify-center gap-2" type="submit">
                <span class="material-symbols-outlined">analytics</span>
                Cek Hasil
              </button>
            </div>
            
            <div class="flex gap-stack-md p-4 bg-error-container/10 border-l-4 border-error rounded-r-lg">
              <span class="material-symbols-outlined text-error">info</span>
              <p class="font-label-md text-error leading-tight text-xs">
                Catatan: Alat ini hanya untuk skrining awal dan bukan diagnosis medis final. Segera hubungi dokter jika gejala memburuk.
              </p>
            </div>
          </form>
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
const formSection = ref(null);

const formData = ref({
  JenisKelamin: '',
  Umur: null,
  Alamat: '',
  gejala: {
    BatukKering: 0,
    BatukBerdahak: 0,
    Demam: 0,
    Pilek: 0,
    HidungTersumbat: 0,
    SesakNapas: 0,
    NyeriTenggorokan: 0,
    SakitKepala: 0,
    MualMuntah: 0,
    NyeriDada: 0,
    SuaraSerak: 0,
    NafsuMakanMenurun: 0,
    HilangPenciuman: 0,
    NyeriSaatMenelan: 0
  }
});

const gejalaList = [
  { key: 'BatukKering', label: 'Batuk Kering (Bk)' },
  { key: 'BatukBerdahak', label: 'Batuk Berdahak (Bb)' },
  { key: 'Demam', label: 'Demam (Dm)' },
  { key: 'Pilek', label: 'Pilek (Pl)' },
  { key: 'HidungTersumbat', label: 'Hidung Tersumbat (Ht)' },
  { key: 'SesakNapas', label: 'Sesak Napas (Sn)' },
  { key: 'NyeriTenggorokan', label: 'Nyeri Tenggorokan (Nt)' },
  { key: 'SakitKepala', label: 'Sakit Kepala (Sk)' },
  { key: 'MualMuntah', label: 'Mual Muntah (Mm)' },
  { key: 'NyeriDada', label: 'Nyeri Dada (Nd)' },
  { key: 'SuaraSerak', label: 'Suara Serak (Ss)' },
  { key: 'NafsuMakanMenurun', label: 'Nafsu Makan Menurun (Nmm)' },
  { key: 'HilangPenciuman', label: 'Hilang Penciuman (Hp)' },
  { key: 'NyeriSaatMenelan', label: 'Nyeri Saat Menelan (Nsm)' }
];

const submitDiagnosis = () => {
    alert('Hasil akan dikirim ke dashboard Anda. Cek console browser untuk melihat data.');
    console.log('Data Formulir:', formData.value);
}

onMounted(() => {
  gsap.to('.diagnosis-card', {
    scrollTrigger: {
      trigger: formSection.value,
      start: 'top 80%',
      toggleActions: 'play reverse play reverse'
    },
    y: 0,
    opacity: 1,
    duration: 1,
    ease: "power3.out"
  });
});
</script>