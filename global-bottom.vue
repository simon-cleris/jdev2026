<template>
  <div class="logos-bar">
    <img src="./assets/LOGO_CNRS_BLEU.png" alt="CNRS" />
    <img src="./assets/laero.jpg" alt="LA&eacute;ro" />
    <img src="./assets/IAGOS_Logo_Color.png" alt="IAGOS" />
    <img src="./assets/banniere_jdev26.png" alt="JDEV 2026" />
  </div>
</template>

<style scoped>
.logos-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 20px;
  background: white;
  display: flex;
  align-items: center;
  justify-content: right;
  gap: 32px;
  padding: 0 24px;
  z-index: 100;
}

.logos-bar img {
  height: 16px;
  width: auto;
  object-fit: contain;
}
</style>
