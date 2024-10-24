<template>
  <section id="projects">
    <div class="info-container">
      <h3 class="title">Projects</h3>
      <div class="project" ref="projectContainer">
        <!-- 영화 프로젝트 -->
        <div class="project-item" @click="openModal('영화 프로젝트')">
          <img
            src="/movie.png"
            alt="영화 프로젝트"
            class="project-img movie-pjt"
          />
          <div class="project-name">영화 프로젝트</div>
        </div>
        <!-- 포트폴리오 프로젝트 -->
        <div class="project-item" @click="openModal('포트폴리오')">
          <img
            src="/portfolio.png"
            alt="포트폴리오"
            class="project-img portfolio-pjt"
          />
          <div class="project-name">포트폴리오</div>
        </div>
        <!-- O2O 프로젝트 -->
        <div class="project-item" @click="openModal('O2O')">
          <img src="/o2o.png" alt="O2O" class="project-img O2O-pjt" />
          <div class="project-name">O2O</div>
        </div>
        <!-- 새싹농부 프로젝트 -->
        <div class="project-item" @click="openModal('sproutfarmer')">
          <img
            src="/sproutfarmer.png"
            alt="O2O"
            class="project-img sproutfarmer-pjt"
          />
          <div class="project-name">새싹농부</div>
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
import { ref, onMounted, onUnmounted } from "vue";

const isModalOpen = ref(false);
const modalTitle = ref("");
const modalContent = ref("");
const modalLanguages = ref("");
const modalGithub = ref("");
const modalDate = ref("");
const modalPeople = ref("");

const projectContainer = ref(null);

const projectDetails = {
  "영화 프로젝트": {
    date: "2024.05.12 ~ 2024.05.23 (1주)",
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
  O2O: {
    date: "2024.07.08 ~ 2024.08.16 (6주)",
    people: "6인 프로젝트(FE_3, BE_3)",
    description: "복잡한 비품 대여 간편화 서비스",
    languages:
      '<img src="https://img.shields.io/badge/html-5C6B81?style=for-the-badge&logo=html5&logoColor=white" />' +
      '<img src="https://img.shields.io/badge/css-264DE4?style=for-the-badge&logo=css3&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" /> ' +
      ' <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"/>',
    github: "https://github.com/iheeya/O2O",
  },
  sproutfarmer: {
    date: "2024.08.19 ~ 2024.10.11 (7주)",
    people: "7인 프로젝트(FE_3, BE_2, DT_2)",
    description: "초보 농부들을 위한 맞춤형 가이드 서비스",
    languages:
      '<img src="https://img.shields.io/badge/html-5C6B81?style=for-the-badge&logo=html5&logoColor=white" />' +
      '<img src="https://img.shields.io/badge/css-264DE4?style=for-the-badge&logo=css3&logoColor=white" /> ' +
      '<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" /> ' +
      ' <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"/>' +
      ' <img src="https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=black"/>',
    github: "https://github.com/iheeya/sproutfarmer",
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

// 스크롤을 통해 움직이도록 만듬
const handleScroll = (event) => {
  if (projectContainer.value) {
    // 스크롤 방향 체크
    const scrollDirection = event.deltaY > 0 ? 1 : -1;

    // 스크롤 위치 조정
    projectContainer.value.scrollLeft += scrollDirection * 50; // 스크롤 속도 조정

    // 전체 화면이 함께 움직이지 않도록
    event.preventDefault();
  }
};

onMounted(() => {
  if (projectContainer.value) {
    projectContainer.value.addEventListener("wheel", handleScroll);
  }
});

onUnmounted(() => {
  if (projectContainer.value) {
    projectContainer.value.removeEventListener("wheel", handleScroll);
  }
});
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
  max-width: calc(100% - 20px);
  margin-left: 30px;
}

.project {
  display: flex;
  overflow-x: hidden; /* 넘치는 경우 가로 스크롤을 숨김 */
  white-space: nowrap; /* 내부 요소들이 줄바꿈되지 않도록 설정 */
  background-color: rgb(179, 111, 111);
  padding-top: 3px;
  margin-top: 30px;
  padding-bottom: 3px;
  margin-right: 20px;
}

.project-item {
  position: relative;
  overflow: hidden;
  margin-right: 3px;
  margin-left: 3px;
  padding: 5px;
  cursor: pointer;
  flex: 0 0 auto; /* 요소가 줄 바꿈되지 않고 스크롤 가능하도록 설정 */
}

.project-img {
  width: 100%;
  height: 250px;
  object-fit: cover; /* 이미지 비율 유지 */
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
  max-height: 70%;
  overflow-y: auto;
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

  .project-img {
    width: 100%;
    height: 150px;
    object-fit: cover;
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

  .info-container {
    margin-right: 180px;
    margin-right: 180px;
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
    margin-right: 180px;
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
    margin-right: 40px;
  }
}
</style>
