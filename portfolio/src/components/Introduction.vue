<template>
  <section id="introduce">
    <h3>About Me</h3>
    <br />
    <p>짧은 자기 pr</p>
    <p>name : 최다희</p>
    <p>age : 1999.10.03</p>
    <p>mail : dahee4918@gmail.com</p>
    <!-- 깃허브 클릭하면 이동하도록 만들기 -->
    <p>
      <a
        href="https://github.com/iheeya"
        target="_blank"
        style="color: white; text-decoration: none"
      >
        github : https://github.com/iheeya
      </a>
    </p>
  </section>
</template>

<script setup></script>

<style scoped>
section {
  display: block;
}

/* Mobile - Portrait */
@media (max-width: 575px) {
  section h3 {
    font-size: 40px;
  }

  section p {
    font-size: 20px;
  }
}

/* Mobile - Landscape */
@media (min-width: 576px) and (max-width: 767px) {
  section h3 {
    font-size: 40px;
  }

  section p {
    font-size: 20px;
  }
}

/* Tablet */
@media (min-width: 768px) and (max-width: 991px) {
  section h3 {
    font-size: 50px;
  }

  section p {
    font-size: 30px;
  }
}

/* Desktop */
@media (min-width: 992px) and (max-width: 1199px) {
  section h3 {
    font-size: 50px;
  }

  section p {
    font-size: 30px;
  }
}

/* Desktop (Large) */
@media (min-width: 1200px) {
  section h3 {
    font-size: 60px;
  }

  section p {
    font-size: 40px;
  }
}
</style>
