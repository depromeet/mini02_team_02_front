<template>
	<div id="wrapper">
		<div id="message">
			<p>아래 선택에 맞게 입력해주세요.</p>
			<p>분실 하신 물건의 습득 상황 검색을 빠르게 도와드립니다:)</p>
		</div>

		<table id="total">
      <tr>
        <td class="col1" v-if="!categoryDown">분실물 종류</td>
        <td class="col1-1" v-if="categoryDown"><p>분실물 종류</p></td>
        <td class="col2">
          <div v-if="!categoryDown" class="select">
            <span> 잃어버린 물건의 카테고리를 선택해주세요. </span>
            <img src="../assets/bt_down.png" @click="categoryDown=true"/>
          </div>
          <div class="category" v-if="categoryDown">
            <span>분실물 종류를 선택해주세요.</span>
            <img id="up" src="../assets/bt_up.png" @click="categoryDown=false"/>

            <table id="options">
              <tr>
                <td>
                  <img class="option" src="../assets/cate_shoppingbag.png" />
                  <p class="korean">쇼핑백</p>
                  <p class="english">Shopping Bag</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_wallet.png" />
                  <p class="korean">지갑</p>
                  <p class="english">Wallet</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_documents.png" />
                  <p class="korean">서류봉투</p>
                  <p class="english">Document</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_book.png" />
                  <p class="korean">책</p>
                  <p class="english">Book</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_bag.png" />
                  <p class="korean">가방</p>
                  <p class="english">Bag</p>
                </td>
              </tr>
              <tr>
                <td>
                  <img class="option" src="../assets/cate_cellphone.png" />
                  <p class="korean">핸드폰</p>
                  <p class="english">Cell Phone</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_file.png" />
                  <p class="korean">파일</p>
                  <p class="english">File</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_backpack.png" />
                  <p class="korean">배낭</p>
                  <p class="english">Backpack</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_clothes.png" />
                  <p class="korean">옷</p>
                  <p class="english">Clothes</p>
                </td>
                <td>
                  <img class="option" src="../assets/cate_etc.png" />
                  <p class="korean">기타</p>
                  <p class="english">etc.</p>
                </td>
              </tr>
            </table>
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
        <td class="col1" v-if="!placeDownDown">분실 장소</td>
        <td class="col1-1" v-if="placeDownDown"><p>분실 장소</p></td>
        <td class="col2">
          <div class="select" v-if="!placeDownDown">
            <span>분실하신 장소를 선택해주세요.</span>
            <img src="../assets/bt_down.png" @click="placeDownDown=true" />
          </div>
          <div class="place-options" v-if="placeDownDown">
            <span>분실 장소를 선택해주세요.</span>
            <img id="up" src="../assets/bt_up.png" @click="placeDownDown=false"/>

            <ul id="place-list">
              <li class="place-option">버스</li>
              <li class="place-option">마을버스</li>
              <li class="place-option">지하철 1~4호선</li>
              <li class="place-option">지하철 5~8호선</li>
              <li class="place-option">지하철 9호선</li>
              <li class="place-option">코레일</li>
              <li class="place-option">법인택시</li>
              <li class="place-option">개인택시</li>
            </ul>
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
      categoryDown: false,
      placeDownDown: false
    }
  },
  methods: {
    toggleCategory: function() {

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
  margin-bottom: 40px;
}

#message p {
  margin: 13px;
}

#total {
  margin-top: 59px;
  text-align: left;
  margin: 0 auto;
  font-size: 24.5px;
}

#total tr>td {
  padding-bottom: 14px;
}

.col1 {
  width: 150px;
  height: 56px;
}

.col1-1 {
  width: 150px;
  height: 56px;
  vertical-align: top;
  /*margin-top: 10px;*/
}

.col1-1 p {
  margin-top: 15px;
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

.select span, .category span, .place-options span {
  width: 26px;
  height: 15px;
  font-size: 15px;
  color: #afafaf;
  margin-top: 19px;
  margin-left: 24px;
  margin-right: 0px;
  width: 500px;
  /*vertical-align: baseline;*/
  display: inline-block;
}

.select img, .category #up, .place-options #up {
  float: right;
  margin-right: 21px;
  margin-top: 21px;
  display: inline;
  /*margin-bottom: 21px;*/
  /*padding-bottom: 100px;*/
}

.category {
  width: 631px;
  height: 324px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
  text-align: center;
}

.place-options {
  width: 631px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
  text-align: center;
}

/*.option {
  float: left;
  display: block;
}*/

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
  /*margin-top: 7px;*/
  /*padding-top: 10px;*/
  margin-right: 6px;
  display: inline-block;
}

#options {
  margin: 0 auto;
  margin-top: 30px;
  text-align: center;
}

#options td {
  height: 90px;
  width: 100px;
}

.korean {
  font-size: 16px;
  color: #333333;
  margin-top: 12px;
  margin-bottom: 5px;
}

.english {
  font-size: 10px;
  color: #989898;
  margin-top: 0px;
}

#place-list {
  text-align: left;
  list-style: none;
  font-size: 20px;
  color: #333333;
  padding: 0;
  margin-bottom: 0;
}

.place-option {
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 50px;
  border-top: solid 1px #dcdcdc;
}
</style>
