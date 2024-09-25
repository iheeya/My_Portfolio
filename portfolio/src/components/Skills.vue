<template>
  <section id="skills">
    <div class="info-container">
      <h3 class="title">Skills</h3>
      <p>Language</p>
      <div class="skills-icons">
        <img
          src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"
        />
      </div>
      <p>Frontend</p>
      <div class="skills-icons">
        <img
          src="https://img.shields.io/badge/vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white"
        />
        <img
          src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white"
        />
        <img
          src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"
        />

        <img
          src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"
        />
        <img
          src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"
        />
        <img
          src="https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=black"
        />
        <img
          src="https://img.shields.io/badge/redux-764ABC?style=for-the-badge&logo=redux&logoColor=black"
        />
      </div>

      <p>Backend</p>
      <div class="skills-icons">
        <img
          src="https://img.shields.io/badge/django-092E20?style=for-the-badge&logo=django&logoColor=white"
        />
      </div>
      <p>Tool</p>
      <div class="skills-icons">
        <img
          src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"
        />
        <img
          src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white"
        />
        <img
          src="https://img.shields.io/badge/gitlab-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white"
        />
        <img
          src="https://img.shields.io/badge/figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white"
        />
      </div>
      <p>DB</p>
      <div class="skills-icons">
        <img
          src="https://img.shields.io/badge/sqlite-003B57?style=for-the-badge&logo=sqlite&logoColor=white"
        />
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
#skills {
  margin-top: 50px;
}
.title {
  color: rgb(179, 111, 111);
  margin-bottom: 30px;
}

.info-container p {
  margin-top: 30px;
}

.skills-icons {
  display: block;
}

.skills-icons img {
  margin-left: 3px; /* 이미지 사이에 여백 추가 */
  margin-right: 3px;
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

  #skills {
    margin-bottom: 150px;
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

  #skills {
    margin-bottom: 150px;
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

  #skills {
    margin-bottom: 150px;
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

  #skills {
    margin-bottom: 150px;
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
    padding-bottom: 180px;
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

  #skills {
    margin-bottom: 150px;
  }
}
</style>
