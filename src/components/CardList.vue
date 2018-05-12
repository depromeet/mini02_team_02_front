<template>
<div class="cardListWrapper">
  <Loading class="loading" />
  <p>검색결과 {{ items.length }}개의 분실물이 나왔습니다</p>
  <div class="cardList">
    <Card v-for="item in items" :data="item" />
  </div>
</div>
</template>

<script>
import Loading from '@/assets/img_bike.svg';
import Card from '@/components/Card';

export default {
  components: {
    Loading,
    Card,
  },
  props: ['items'],
};
</script>

<style scoped>
.cardListWrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.cardList {
  width: 1300px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  flex-wrap: wrap;
}
.loading {
  margin-top: 110px;
}
p {
  font-size: 20.5px;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.34;
  letter-spacing: normal;
  text-align: center;
  color: #333333;
}
</style>