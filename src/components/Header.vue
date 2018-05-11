<template>
<div class="header">
  <div class="headerInner">
    <Logo class="logo" />
    <div>
      <button class="button">마이페이지</button>
      <button class="button">주인을 찾아요</button>
    </div>
  </div>
</div>
</template>

<script>
import Logo from '@/assets/logo_header.svg';

export default {
  components: {
    Logo,
  },
};
</script>

<style scoped>
.logo {
  width: 221px;
  height: 56px;
}
.header {
  height: 100px;
  background: transparent;
  display: flex;
  position: relative;
  z-index: 100;
}
.header .headerInner {
  width: 1950px;
  padding: 0 100px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.button {
  width: 225px;
  height: 48px;
  background: #0a52b3;
  color: #fff;
  border-radius: 24px;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 0.25;
  letter-spacing: normal;
  text-align: center;
  color: #fffef3;
  outline: none;
  cursor: pointer;
}
.button:not(:last-child) {
  margin-right: 18px;
}
</style>
