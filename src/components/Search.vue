<template>
	<div id="wrapper">
		<div id="message">
			<p>아래 선택에 맞게 입력해주세요.</p>
			<p>분실 하신 물건의 습득 상황 검색을 빠르게 도와드립니다:)</p>
		</div>

		<table>
      <tr>
        <td class="col1">분실물 종류</td>
        <td class="col2">
          <div class="select">
            <span> 잃어버린 물건의 카테고리를 선택해주세요. </span>
            <img src="../assets/bt_down.png" v-click="categoryDown=1"/>
            <!-- <img v-if="categoryDown === 1" src="../assets/bt_up.png" v-click="categoryDown=0"/> -->
          </div>
        </td>
      </tr>
      <tr>
        <td class="col1">분실물 명</td>
        <td class="col2">
          <input id="lost-name" type="text" placeholder="      잃어버린 물건의 이름을 입력해주세요." />
        </td>
      </tr>
      <tr>
        <td class="col1">기간</td>
        <td class="col2">
          <div>
            <input class="lost-date" type="text" placeholder="      2018.05.12" />
            <img class="cal-icon" src="../assets/bt_calendar.png" align="middle" />
            <span id="char">~</span>
            <input class="lost-date" type="text" placeholder="      2018.05.12">
            <img class="cal-icon" src="../assets/bt_calendar.png" align="middle"/>
          </div>
        </td>
      </tr>
      <tr>
        <td class="col1">분실 장소</td>
        <td class="col2">
          <div class="select">
            <span>분실하신 장소를 선택해주세요.</span>
            <img src="../assets/bt_down.png" v-click="placeDown=1" />
            <!-- <img v-if="placeDown === 1" src="../assets/bt_up.png" v-click="placeDown=0" /> -->
          </div>
        </td>
      </tr>

		</table>

    <button id="search">
      <div id="search-wrapper">
        <img id="search-icon" src="../assets/icon_search.png"/>
        <span>검색하기</span>
      </div>
    </button>
	</div>
</template>

<script>
export default {
  name: 'Card',
  data () {
    return {
      categoryDown: 0,
      placeDown: 0
    }
  }
}

</script>

<style scoped>
@import url(https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css);

#wrapper {
  background-color: #f4f4f4;
  width: 100%;
  font-family: 'NanumSquare';
}

#message {
  font-size: 34.4px;
  color: #333333;
}

#message p {
  margin: 13px;
}

table {
  margin-top: 59px;
  text-align: left;
  margin: 0 auto;
  font-size: 24.5px;
}

tr>td {
  padding-bottom: 14px;
}

.col1 {
  width: 150px;
  height: 56px;
}

.col2 {
  height: 56px;
}

#char {
  margin-left: 15px;
  margin-right: 15px;
}

.select {
  width: 631px;
  height: 56px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
}

.select span {
  font-size: 15px;
  color: #afafaf;
  margin-top: 19px;
  margin-left: 24px;
  margin-right: 0px;
  width: 500px;
  /*vertical-align: baseline;*/
  display: inline-block;
}

.select img {
  float: right;
  margin-right: 21px;
  margin-top: 21px;
  display: inline;
  /*margin-bottom: 21px;*/
  /*padding-bottom: 100px;*/
}

#lost-name {
  width: 631px;
  height: 56px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
  /*display: inline-block;*/
}

.lost-date {
  width: 218px;
  height: 56px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
}

input::placeholder {
  font-size: 15px;
  color: #afafaf;
  margin-top: 21px;
  margin-left: 24px;
  font-family: 'NanumSquare';
}

.cal-icon {
  height: 44px;
  width: 51px;
  margin-left: 10px;
  /*margin-top: 6px;*/
  margin-bottom: 10px;
  display: inline-block;
}

#search {
  width: 280px;
  height: 55px;
  border-radius: 27.5px;
  background-color: #0a52b3;
  font-size: 19.5px;
  color: #ffffff;
  border: none;
  margin-top: 40px;
}

#search-wrapper {
  /*margin-top: 18px;*/
}

#search-icon {
  width: 20px;
  height: 20px;
  /*padding-top: 7px;*/
  /*padding-top: 10px;*/
  margin-right: 6px;
}
</style>
