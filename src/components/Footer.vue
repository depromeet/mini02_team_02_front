<template>
<footer>
  <div class="footerWrapper">
    <div>
      <p>Depromet. 디자이너와 프로그래머가 만났을 때</p>
      <p>Miniproject 2nd.</p>
      <p>2018.04.28 - 2018.05.12</p>
    </div>
    <div>
      <img class="logo" src="../assets/logo_footer.png" />
      <img class="logo" src="../assets/logo_depromet.png" />
    </div>
    <div>
      <p>Design. YoungEun. DaWon.</p>
      <p>Front. JaeWon. YeGi.</p>
      <p>Back. JongHoon. JuHyun.</p>
    </div>
  </div>
</footer>
</template>

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
.logo:not(:first-child) {
  margin-left: 20px;
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