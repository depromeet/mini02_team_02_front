<template>
<div class="header">
  <div class="headerInner">
    <Logo class="logo" />
    <div class="button-group">
      <button class="button">
        <MyPage />
        마이페이지
      </button>
      <button class="button">
        <Find />
        주인을 찾아요
      </button>
    </div>
  </div>
</div>
</template>

<script>
import Logo from '@/assets/logo_header.svg';
import MyPage from '@/assets/icon_mypage.svg';
import Find from '@/assets/icon_find.svg';

export default {
  components: {
    Logo,
    MyPage,
    Find,
  },
};
</script>

<style scoped>
.logo {
  width: 221px;
  height: 56px;
  cursor: pointer;
}
.header {
  height: 120px;
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
.button-group {
  display: flex;
  flex-direction: row;
  justify-content: center;
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
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
}
.button:not(:last-child) {
  margin-right: 18px;
}
.button svg {
  margin-right: 12px;
}
</style>
