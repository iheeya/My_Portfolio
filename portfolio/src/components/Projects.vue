<template>
  <section id="introduce">
    <div class="info-container">
      <h3 class="title">Projects</h3>
      <div class="project">
        <img src="/movie.png" alt="영화 프로젝트" class="movie-pjt" />
        <img src="/portfolio.png" alt="포트폴리오" class="portfolio-pjt" />
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
/* .movie-pjt{
  width: ;
} */
.title {
  color: rgb(179, 111, 111);
}
/* Mobile - Portrait */
@media (max-width: 575px) {
  section h3 {
    font-size: 40px;
  }

  .info-container p {
    font-size: 20px;
  }

  .info-container {
    margin-left: 30px;
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
    font-size: 22px;
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
    font-size: 30px;
  }

  .info-container {
    margin-left: 190px;
  }
}

/* 데스크탑 화면 분할 미디어 쿼리 */
@media (min-width: 600px) and (max-width: 900px) {
  section h3 {
    font-size: 45px;
  }

  .info-container p {
    font-size: 22px;
  }

  .info-container {
    margin-left: 40px;
  }
}
</style>
