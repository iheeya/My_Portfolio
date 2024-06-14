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
        <p>{{ modalContent }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isModalOpen = ref(false);
const modalTitle = ref("");
const modalContent = ref("");

// 프로젝트 상세 내용을 저장하는 객체
const projectDetails = {
  "영화 프로젝트":
    "영화 프로젝트의 상세 내용입니다. 이 프로젝트는 영화 데이터를 분석하고 시각화하는 프로젝트입니다.",
  포트폴리오:
    "포트폴리오 프로젝트의 상세 내용입니다. 이 프로젝트는 개인 포트폴리오 웹사이트를 만드는 프로젝트입니다.",
};

const openModal = (title) => {
  modalTitle.value = title;
  modalContent.value = projectDetails[title]; // 제목에 맞는 상세 내용을 설정
  console.log(title, modalTitle.value, modalContent.value); // 콘솔 로그 확인
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
  background-color: rgb(0, 0, 0);
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
