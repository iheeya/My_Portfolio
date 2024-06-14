<template>
  <section id="projects">
    <div class="info-container">
      <h3 class="title">Projects</h3>
      <div class="project">
        <div class="project-item" @click="openModal('영화 프로젝트')">
          <img
            src="/movie.png"
            alt="영화 프로젝트"
            class="project-img movie-pjt"
          />
          <div class="project-name">영화 프로젝트</div>
        </div>
        <div class="project-item" @click="openModal('포트폴리오')">
          <img
            src="/portfolio.png"
            alt="포트폴리오"
            class="project-img portfolio-pjt"
          />
          <div class="project-name">포트폴리오</div>
        </div>
      </div>
    </div>
  </section>

  <div v-if="isModalOpen" class="modal">
    <div class="modal-content">
      <span class="close" @click="closeModal">&times;</span>
      <div class="modal-title">{{ modalTitle }}</div>
      <div class="modal-body">
        <p>{{ modalDate }}</p>
        <p>{{ modalPeople }}</p>
        <p>{{ modalContent }}</p>
        <p>
          <span v-html="modalLanguages"></span>
        </p>
        <p>
          <a :href="modalGithub" target="_blank" class="github">
            <i class="fab fa-github"></i> More Info in GitHub
          </a>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isModalOpen = ref(false);
const modalTitle = ref("");
const modalContent = ref("");
const modalLanguages = ref("");
const modalGithub = ref("");
const modalDate = ref("");
const modalPeople = ref("");

const projectDetails = {
  "영화 프로젝트": {
    date: "2024.05.12 ~ 2024.05.23",
    people: "2인 프로젝트",
    description:
      "영화 보는 것을 좋아하는 사람들을 위한 웹사이트. 사용자가 좋아하는 영화를 기반으로 영화를 추천해주고, 영화에 대해 토론할 수 있는 웹 사이트를 만들고자 했습니다.",
    languages:
      '<img src="https://img.shields.io/badge/html-5C6B81?style=for-the-badge&logo=html5&logoColor=white" />' +
      '<img src="https://img.shields.io/badge/css-264DE4?style=for-the-badge&logo=css3&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" /> ' +
      '<img src="https://img.shields.io/badge/vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/django-092E20?style=for-the-badge&logo=django&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/sqlite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" />',
    github: "https://github.com/iheeya/Movie-PJT",
  },
  포트폴리오: {
    date: "2024.06 ~ still updating..",
    people: "1인 프로젝트",
    description:
      "나의 포트폴리오를 한 눈에 볼 수 있도록 웹 사이트로 만들었습니다.",
    languages:
      '<img src="https://img.shields.io/badge/html-5C6B81?style=for-the-badge&logo=html5&logoColor=white" />' +
      '<img src="https://img.shields.io/badge/css-264DE4?style=for-the-badge&logo=css3&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" /> ' +
      '<img src="https://img.shields.io/badge/vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white" />',
    github: "https://github.com/iheeya/My_Portfolio",
  },
};

const openModal = (title) => {
  modalTitle.value = title;
  modalContent.value = projectDetails[title].description;
  modalLanguages.value = projectDetails[title].languages;
  modalGithub.value = projectDetails[title].github;
  modalDate.value = projectDetails[title].date;
  modalPeople.value = projectDetails[title].people;
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
};
</script>

<style scoped>
#projects {
  margin-bottom: 200px;
}

.github {
  text-decoration: none;
  color: rgb(179, 111, 111);
}

.title {
  color: rgb(179, 111, 111);
  margin-bottom: 80px;
}

.info-container {
  max-width: calc(
    100% - 20px
  ); /* 전체 화면에서 20px 뺀 값만큼 최대 너비 설정 */
  margin-left: 30px; /* 기존 마진 유지 */
}

.project {
  display: flex;
  background-color: rgb(179, 111, 111);
  padding-top: 3px;
  margin-top: 30px;
  padding-bottom: 3px;
  margin-right: 200px; /* 오른쪽 여백 설정 */
}

.project-item {
  position: relative;
  overflow: hidden;
  margin-right: 3px;
  margin-left: 3px;
  padding: 5px;
  cursor: pointer; /* 클릭 가능하도록 포인터 커서 추가 */
}

.project-img {
  transition: opacity 0.3s ease;
}

.project-name {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: transparent;
  font-size: 24px;
  font-weight: bold;
}

.project-item:hover .project-img {
  opacity: 0.2;
}

.project-item:hover .project-name {
  color: white;
}

/* 모달 스타일 */
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.8);
}

.modal-content {
  background-color: rgb(55, 55, 55);
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
  max-width: 600px;
  text-align: center;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.modal-title {
  font-size: 24px;
  font-weight: bold;
  margin-top: 10px;
}

.modal-body {
  font-size: 18px;
  margin-top: 20px;
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
