<template>
  <div style="margin: 0px">
    <header class="navbar">
      <div class="logo">
        <a @click="scrollToSection('about-me')" class="logo">CHOIDAHEE</a>
      </div>
      <nav>
        <ul>
          <li><a @click="scrollToSection('introduce')">About Me</a></li>
          <li><a @click="scrollToSection('skills')">Skills</a></li>
          <li><a @click="scrollToSection('projects')">Projects</a></li>
        </ul>
      </nav>
    </header>

    <Me id="about-me" />
    <Introduction id="introduce" />
    <Skills id="skills" />
    <Projects id="projects" />
  </div>

  <footer class="footer">&copy; 2024 HEE's Protfolio by Dahee Choi</footer>
</template>

<script setup>
import { ref, onMounted } from "vue";
import Me from "./components/Me.vue";
import Introduction from "./components/Introduction.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";

const scrollToSection = (id) => {
  const element = document.getElementById(id);
  if (element) {
    const navbarHeight = document.querySelector(".navbar").offsetHeight;
    const offset = element.offsetTop - navbarHeight;
    window.scrollTo({
      top: offset,
      behavior: "smooth",
    });
  }
};

onMounted(() => {
  // 초기화나 렌더링 이후에 필요한 초기화 코드 추가
});
</script>

<style scoped>
/* 전체 화면 배경 색 적용 */
:global(body) {
  background-color: rgb(55, 55, 55);
  margin: 0;
  padding: 0;
  font-family: "Roboto", sans-serif; /* 공항 안내 방송 기사를 참조하여 수정 */
  color: #ffffff; /* 영화에서 */
}

/* 헤더바 스타일링 */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 45px;
  background-color: rgb(55, 55, 55);
  color: white;
  opacity: 0.9;
  /* nav바 상단 고정 */
  position: sticky;
  top: 0;
  z-index: 1000; /* 네비게이션 바가 다른 요소 위에 나타나도록 설정 */
}

.logo {
  color: white;
  text-decoration: none;
}

nav ul {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}

nav ul li {
  margin: 0;
}

nav ul li a {
  color: white;
  text-decoration: none;
}

/* 각 섹션이 화면의 전체 높이를 차지하도록 설정 */
section {
  /* height: 100vh; 화면의 전체 높이 */
  display: flex;
  /* padding: 20px; */
}

.portfolio {
  padding: 20px;
}

.head {
  font-size: 30px;
}

/* 고정된 위치의 footer 스타일링 */
.footer {
  bottom: 0;
  width: 100%;
  text-align: center;
  padding: 10px 0;
  background-color: rgb(55, 55, 55);
  color: white;
  font-size: 14px;
}

/* Mobile - Portrait */
@media (max-width: 575px) {
  nav ul li a {
    font-size: 15px;
  }

  nav ul {
    gap: 20px;
  }

  .logo {
    font-size: 15px;
  }
}

/* Mobile - Landscape */
@media (min-width: 576px) and (max-width: 767px) {
  nav ul li a {
    font-size: 15px;
  }

  nav ul {
    gap: 30px;
  }

  .logo {
    font-size: 15px;
  }
}

/* Tablet */
@media (min-width: 768px) and (max-width: 991px) {
  nav ul li a {
    font-size: 18px;
  }

  nav ul {
    gap: 30px;
  }

  .logo {
    font-size: 18px;
  }
}

/* Desktop */
@media (min-width: 992px) and (max-width: 1199px) {
  nav ul li a {
    font-size: 20px;
  }

  nav ul {
    gap: 40px;
  }

  .logo {
    font-size: 20px;
  }
}

/* Desktop (Large) */
@media (min-width: 1200px) {
  nav ul li a {
    font-size: 20px;
  }

  nav ul {
    gap: 40px;
  }

  .logo {
    font-size: 20px;
  }
}

/* 데스크탑 화면 분할 미디어 쿼리 */
@media (min-width: 600px) and (max-width: 900px) {
  nav ul li a {
    font-size: 20px;
  }

  nav ul {
    gap: 40px;
  }

  .logo {
    font-size: 20px;
  }
}
</style>
