<template>
    <div id="skip">
      <a href="#header" @click="scrollLink($event)">헤더 영역 바로가기</a>
      <a href="#intro" @click="scrollLink($event)">소개 영역 바로가기</a>
      <a href="#skill" @click="scrollLink($event)">스킬 영역 바로가기</a>
      <a href="#port" @click="scrollLink($event)">포트폴리오 영역 바로가기</a>
      <a href="#contact" @click="scrollLink($event)">연락처 영역 바로가기</a>
      <a href="#footer" @click="scrollLink($event)">푸터 영역 바로가기</a>
    </div>
</template>

<script>
  export default {
      methods: {
          scrollLink(event) {
              event.preventDefault();

              const targetId = event.target.getAttribute("href");
              const targetElement = document.querySelector(targetId);

              if (targetElement) {
                  targetElement.scrollIntoView({ behavior: "smooth" });
              }
          },
      },
  };
</script>
