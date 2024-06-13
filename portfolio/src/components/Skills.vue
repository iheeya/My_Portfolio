<template>
  <section id="skills">
    <h3>Skills</h3>
    <p>lan</p>
  </section>
</template>

<script setup></script>

<style scoped>
/* 미디어 쿼리 추가 */

/* 세로모드 모바일 디바이스 (가로 해상도가 576px 보다 작은 화면에 적용) */
@media (max-width: 575px) {
  section h3 {
    font-size: 18px;
  }

  section p {
    font-size: 10px;
  }
}

/* 가로모드 모바일 디바이스 (가로 해상도가 768px 보다 작은 화면에 적용) */
@media (max-width: 767px) {
  section h3 {
    font-size: 20px;
  }

  section p {
    font-size: 11px;
  }
}

/* 태블릿 디바이스 (가로 해상도가 992px 보다 작은 화면에 적용) */
@media (max-width: 991px) {
  section h3 {
    font-size: 22px;
  }

  section p {
    font-size: 12px;
  }
}

/* 데스크탑 (가로 해상도가 1200px 보다 작은 화면에 적용) */
@media (max-width: 1199px) {
  section h3 {
    font-size: 24px;
  }

  section p {
    font-size: 12px;
  }
}
</style>
