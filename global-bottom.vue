<template>
  <div class="logos-bar">
    <img src="./assets/laero.jpg" alt="LAERO" />
    <img src="./assets/logo_omp.png" alt="OMP" />
    <img src="./assets/logo_utoulouse.png" alt="Université de Toulouse" />
    <img src="./assets/LOGO_CNRS_BLEU.png" alt="CNRS" />
    <span class="ird">
      <img src="./assets/logoIRD_Horizontal_Baseline_FR_Noir.png" alt="IRD" />
    </span>
  </div>
</template>

<style scoped>
.logos-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 28px;
  background: white;
  display: flex;
  align-items: center;
  justify-content: right;
  gap: 32px;
  padding: 0 24px;
  z-index: 100;
}

.logos-bar > img {
  height: 20px;
  width: auto;
  object-fit: contain;
}

/* Logo IRD : l'image source (3508x2481) a de grandes marges, on recadre
   sur la zone utile (1645x360 à partir de 933,1060) à hauteur de 20px. */
.logos-bar .ird {
  display: block;
  width: 91px;
  height: 20px;
  overflow: hidden;
}

.logos-bar .ird img {
  display: block;
  max-width: none;
  width: 195px;
  margin: -58.9px 0 0 -51.8px;
}
</style>
