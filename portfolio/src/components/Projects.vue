<template>
  <section id="introduce">
    <div class="info-container">
      <h3>Projects</h3>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
/* Mobile - Portrait */
@media (max-width: 575px) {
  section h3 {
    font-size: 40px;
  }

  .info-container p {
    font-size: 20px;
  }
}

/* Mobile - Landscape */
@media (min-width: 576px) and (max-width: 767px) {
  section h3 {
    font-size: 40px;
  }

  .info-container p {
    font-size: 20px;
  }
}

/* Tablet */
@media (min-width: 768px) and (max-width: 991px) {
  section h3 {
    font-size: 50px;
  }

  .info-container p {
    font-size: 30px;
  }
}

/* Desktop */
@media (min-width: 992px) and (max-width: 1199px) {
  section h3 {
    font-size: 50px;
  }

  .info-container p {
    font-size: 30px;
  }
}

/* Desktop (Large) */
@media (min-width: 1200px) {
  section h3 {
    font-size: 60px;
  }

  .info-container p {
    font-size: 38px;
  }
}
</style>
