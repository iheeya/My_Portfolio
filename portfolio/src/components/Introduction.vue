<template>
  <section id="introduce">
    <div class="info-container">
      <h3>About Me</h3>
      <p>name : 최다희</p>
      <p>age : 1999.10.03</p>
      <p><i class="far fa-envelope"></i> : dahee4918@gmail.com</p>

      <!-- 깃허브 클릭하면 이동하도록 만들기 -->
      <p>
        <a
          href="https://github.com/iheeya"
          target="_blank"
          style="color: white; text-decoration: none"
        >
          <i class="fab fa-github"></i> : https://github.com/iheeya
        </a>
      </p>
    </div>

    <div style="text-align: left">
      <h3>hello</h3>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
/* section 내의 div들을 중앙 정렬 */
/* section {
    display: flex;
    justify-content: center;
  } */

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

  .info-container {
    margin-left: 190px;
  }
}
</style>
