<template>
  <div class="Container">
    <!-- Input bileşenleri -->
    <InputComponents v-model="sayi1" placeholder="Sayı 1" />
    <InputComponents v-model="sayi2" placeholder="Sayı 2" />

    <!-- İşlem butonları -->
    <div class="btnContainer">
      <button class="btn" @click="Toplama()">+</button>
      <button class="btn" @click="Cikarma()">-</button>
      <button class="btn" @click="Carpma()">×</button>
      <button class="btn" @click="Bolme()">÷</button>
    </div>

    <hr>

    <!-- Sonuç gösterimi -->
    <div class="sonuc">{{ sonuc }}</div>
  </div>
</template>
<script>
import ActionButton from '@/components/ActionButton.vue';
import InputComponents from '@/components/InputComponents.vue'

export default {
  name: 'Calculator',
  data() {
    return {
      sayi1: null,
      sayi2: null,
      sonuc: null,
    };
  },
  methods: {
    // Toplama işlemi
    Toplama() {
      this.sonuc = parseFloat(this.sayi1) + parseFloat(this.sayi2);
    },
    // Çıkarma işlemi
    Cikarma() {
      this.sonuc = parseFloat(this.sayi1) - parseFloat(this.sayi2);
    },
    // Çarpma işlemi
    Carpma() {
      this.sonuc = parseFloat(this.sayi1) * parseFloat(this.sayi2);
    },
    // Bölme işlemi
    Bolme() {
      this.sonuc = parseFloat(this.sayi1) / parseFloat(this.sayi2);
    },
  },
  components: {
    InputComponents,
    ActionButton,
  }
}
</script>


<style scoped>
.Container {
  width: 200px;
}
.btnContainer {
  display: flex;
  width: 100%;
  justify-content: space-evenly;
  align-items: center;
  margin-top: 10px;
}

.btn {
  width: 30px;
  height: 20px;
  color: #000;
}
.sonuc {
  height: 20px;
  margin-bottom: 10px;
  border: 1px solid #000000;
  padding: 5px;
  border-radius: 10px;
  overflow: hidden;
  color: black;
}
</style>
