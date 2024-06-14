<template>
  <section id="introduce">
    <div class="info-container">
      <h3 class="title">About Me</h3>
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

    <div class="self-introduce">
      <p>
        안녕하세요! 저는 끈기 있게 도전하여 문제를 해결하는 것을 즐기는 신입
        프론트엔드 개발자입니다. <br />
        사용자에게 직관적이고 편리하게 이용할 수 있는 웹 경험을 제공하기 위해
        노력하고 있습니다.
      </p>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.title {
  color: rgb(179, 111, 111);
  margin-bottom: 30px;
}

#introduce {
  padding-bottom: 150px;
  padding-top: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.self-introduce {
  margin-top: 60px;
  color: rgb(179, 111, 111);
  transition: transform 0.3s ease;
}

.self-introduce:hover {
  transform: rotate(-5deg);
}

.info-container {
  flex: 1;
  margin-right: 20px;
}

@media (max-width: 575px) {
  .info-container {
    order: -1;
    margin-right: 0;
    margin-bottom: 20px;
    margin-left: 20px;
  }

  section h3 {
    font-size: 40px;
  }

  .info-container p {
    font-size: 20px;
  }

  .self-introduce {
    margin-top: 20px; /* 원하는 여백으로 조정 */
    margin-left: 20px; /* 원하는 위치로 조정 */
    margin-right: 50px;
  }

  .self-introduce p {
    font-size: 15px;
  }
}

@media (min-width: 576px) and (max-width: 991px) {
  section h3 {
    font-size: 50px;
  }

  .self-introduce p {
    font-size: 20px;
    margin-left: 100px; /* 원하는 위치로 조정 */
    margin-right: 100px;
  }

  .info-container p {
    font-size: 30px;
  }

  .info-container {
    margin-left: 100px;
  }
}

@media (min-width: 992px) and (max-width: 1199px) {
  section h3 {
    font-size: 50px;
  }

  .self-introduce p {
    font-size: 20px;
    margin-left: 190px; /* 원하는 위치로 조정 */
    margin-right: 190px;
  }

  .info-container p {
    font-size: 30px;
  }

  .info-container {
    margin-left: 190px;
  }
}

@media (min-width: 1200px) {
  section h3 {
    font-size: 60px;
  }

  .self-introduce p {
    font-size: 25px;
    margin-left: 190px;
    margin-right: 190px;
  }

  .info-container p {
    font-size: 38px;
  }

  .info-container {
    margin-left: 190px;
  }
}

/* 데스크탑 화면 분할 미디어 쿼리 */
@media (min-width: 600px) and (max-width: 900px) {
  section h3 {
    font-size: 40px;
  }

  .self-introduce p {
    font-size: 15px;
    line-height: 30px;
  }

  .info-container p {
    font-size: 20px;
  }

  .info-container {
    margin-right: 10px;
    margin-left: 100px;
  }
}
</style>
