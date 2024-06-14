<template>
  <section id="about-me">
    <!-- v-html을 사용하여 HTML을 렌더링합니다 -->
    <h3 class="cursor" v-html="formattedHelloText"></h3>
    <div class="arrow-container">
      <i class="fas fa-chevron-down arrow" @click="scrollToNextSection"></i>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

const helloText = ref("");
const formattedHelloText = ref("");

onMounted(() => {
  const text = "Hello, I'm Dahee <br> Front-end Developer";
  let index = 0;
  const interval = setInterval(() => {
    if (index <= text.length) {
      const partialText = text.substring(0, index);
      index++;
      helloText.value = partialText;
      // 줄바꿈 처리된 텍스트 설정
      formattedHelloText.value = partialText;
    } else {
      clearInterval(interval);
    }
  }, 100); // 100ms 간격으로 한 글자씩 출력
});

const scrollToNextSection = () => {
  const aboutMeSection = document.getElementById("about-me");
  const nextSection = aboutMeSection.nextElementSibling;
  if (nextSection) {
    const navbarHeight = document.querySelector(".navbar").offsetHeight;
    const offset = nextSection.offsetTop - navbarHeight;
    window.scrollTo({
      top: offset,
      behavior: "smooth",
    });
  }
};
</script>

<style scoped>
#about-me {
  text-align: center;
  position: relative; /* 부모 요소를 상대 위치로 설정 */
  height: 100vh; /* 화면의 전체 높이를 차지하도록 설정 */
  display: flex;
  flex-direction: column;
  justify-content: flex-start; /* 요소들을 위로 정렬 */
  padding-top: 180px; /* 상단 여백을 추가하여 요소들을 약간 아래로 이동 */
}

/* Common styles */
.cursor {
  display: inline-block; /* h3 요소를 inline-block으로 설정하여 텍스트와 커서가 같은 라인에 위치하도록 합니다. */
  position: relative; /* 상대 위치 설정 */
  white-space: pre-wrap; /* 줄바꿈 유지 */
  color: rgb(179, 111, 111); /* 이 부분에서 Hello 텍스트의 색상을 설정 */
}

.cursor::after {
  content: "|";
  position: relative; /* 상대 위치로 변경하여 텍스트와 수평으로 정렬합니다 */
  top: -0.09em; /* 텍스트와 커서를 수직 정렬합니다 */
  margin-left: 5px; /* 좌측 여백을 추가하여 텍스트와 커서 간의 간격을 조정합니다. */
  animation: cursor 0.7s infinite;
  color: rgb(179, 111, 111); /* 흰색 */
}

.arrow-container {
  position: absolute; /* 절대 위치 설정 */
  bottom: 220px; /* 하단에서 20px 위에 위치 */
  width: 100%; /* 부모 요소의 너비에 맞춤 */
  display: flex;
  justify-content: center; /* 가운데 정렬 */
}

.arrow {
  font-size: 2rem;
  color: white;
  cursor: pointer;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-10px);
  }
  60% {
    transform: translateY(-5px);
  }
}

/* Media queries */
@media (max-width: 575px) {
  section h3 {
    font-size: 40px;
  }
}

@media (min-width: 576px) and (max-width: 767px) {
  section h3 {
    font-size: 40px;
  }
}

@media (min-width: 768px) and (max-width: 991px) {
  section h3 {
    font-size: 50px;
  }
}

@media (min-width: 992px) and (max-width: 1199px) {
  section h3 {
    font-size: 60px;
  }
}

@media (min-width: 1200px) {
  section h3 {
    font-size: 80px;
  }
}

/* 데스크탑 화면 분할 미디어 쿼리 */
@media (min-width: 600px) and (max-width: 900px) {
  section h3 {
    font-size: 60px;
  }
}

@keyframes cursor {
  50% {
    opacity: 0;
  }
}
</style>
