<template>
<footer>
  <div class="footerWrapper">
    <div>
      <p>Depromet. 디자이너와 프로그래머가 만났을 때</p>
      <p>Miniproject 2nd.</p>
      <p>2018.04.28 - 2018.05.12</p>
    </div>
    <div>
      <Logo class="logo"/>
    </div>
    <div>
      <p>Design. YoungEun. DaWon.</p>
      <p>Front. JaeWon. YeGi.</p>
      <p>Back. JongHoon. JuHyun.</p>
    </div>
  </div>
</footer>
</template>

<script>
import Logo from '@/assets/logo_footer.svg';

export default {
  components: {
    Logo,
  },
};
</script>

<style scoped>
footer {
  margin-top: 90px;
  height: 242px;
  background: #434544;
  display: flex;
  justify-content: center;
  align-items: center;
}
.footerWrapper {
  width: 900px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.logo {
  fill: #979797;
  color: #979797;
}
p {
  font-size: 10px;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.95;
  letter-spacing: normal;
  text-align: left;
  color: #9c9c9c;
}
</style>