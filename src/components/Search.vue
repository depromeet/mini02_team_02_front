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
          <div v-if="!categoryDown" class="select" v-bind:class="{ 'selected': categorySelected }" @click="categoryDown=true">
            <span>{{ categorySelected ? categoryName: '잃어버린 물건의 카테고리를 선택해주세요.' }}</span>
            <img src="../assets/bt_down.png"/>
          </div>
          <div class="category" v-if="categoryDown">
            <span>분실물 종류를 선택해주세요.</span>
            <img id="up" src="../assets/bt_up.png" @click="categoryDown=false"/>

            <div id="options">
              <div class="optionItem" v-for="category in categorys">
                <div @click="clickCategory(category.name)">
                  <img class="option" :src="getImgUrl(category.img)"/>
                  <p class="korean">{{ category.name }}</p>
                  <p class="english">{{ category.en }}</p>
                </div>
              </div>
            </div>
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
          <div class="select" v-bind:class="{ 'selected': placeSelected }" v-if="!placeDownDown" @click="clickPlaceDown(true)">
            <span>{{ placeSelected ? placeName: '분실하신 장소를 선택해주세요.' }}</span>
            <img src="../assets/bt_down.png" />
          </div>
          <div class="place-options" v-if="placeDownDown">
            <span>분실 장소를 선택해주세요.</span>
            <img id="up" src="../assets/bt_up.png" @click="clickPlaceDown(false)"/>

            <ul id="place-list">
              <li class="place-option" v-for="place in places" @click="clickPlace(place.name, place.id)">
                {{ place.name }}
              </li>
            </ul>
          </div>
        </td>
      </tr>

		</table>

    <button id="search" @click="searchItems()">
      <div id="search-wrapper">
        <img id="search-icon" src="../assets/icon_search.png"/>
        <span>검색하기</span>
      </div>
    </button>
	</div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Search',
  data () {
    return {
      categorys: [{
        'name': '쇼핑백',
        'en': 'Shopping Bag',
        'img': 'cate_shoppingbag', 
      }, {
        'name': '지갑',
        'en': 'Wallet',
        'img': 'cate_wallet',
      }, {
        'name': '서류통부',
        'en': 'Document',
        'img': 'cate_documents',
      }, {
        'name': '책',
        'en': 'Book',
        'img': 'cate_book',
      }, {
        'name': '가방',
        'en': 'Bag',
        'img': 'cate_bag',
      }, {
        'name': '핸드폰',
        'en': 'Cell Phone',
        'img': 'cate_cellphone',
      }, {
        'name': '파일',
        'en': 'File',
        'img': 'cate_file',
      }, {
        'name': '배낭',
        'en': 'Backpack',
        'img': 'cate_backpack',
      }, {
        'name': '옷',
        'en': 'Clothes',
        'img': 'cate_clothes',
      }, {
        'name': '기타',
        'en': 'etc.',
        'img': 'cate_etc',
      }],
      categoryName: null,
      categorySelected: false,
      categoryDown: false,
      places: [{
        'name': '버스',
        'id': 'b1',
      }, {
        'name': '마을버스',
        'id': 'b2',
      }, {
        'name': '지하철 1~4호선',
        'id': 's1',
      }, {
        'name': '지하철 5~8호선',
        'id': 's2',
      }, {
        'name': '지하철 9호선',
        'id': 's4',
      }, {
        'name': '코레일',
        'id': 's3',
      }, {
        'name': '법인택시',
        'id': 't1',
      }, {
        'name': '개인택시',
        'id': 't2',
      }],
      placeName: null,
      placeId: null,
      placeSelected: false,
      placeDownDown: false,
    }
  },
  methods: {
    getImgUrl(img) {
      var images = require.context('../assets/', false, /\.png$/)
      return images('./' + img + ".png")
    },
    toggleCategory: function() {
    },
    clickCategory: function(name) {
      this.categoryName = name;
      this.categorySelected = true;
      this.categoryDown = false;
    },
    clickPlaceDown: function(click) {
      this.placeDownDown = click;
      this.placeSelected = !click;
    },
    clickPlace: function(name, id) {
      this.placeName = name;
      this.placeId = id;
      this.placeSelected = true;
      this.placeDownDown = false;
    },
    searchItems: function() {
      var self = this;
      axios.get('http://13.209.42.155:8080/Greeting/losts', {
        params: {
          category: this.categoryName,
          place: this.placeId,
        },
        headers: {
          'Access-Control-Allow-Origin': '*',
          'Content-Type': 'application/json',
        },
      }).then(res => {
        // this.items = res;
        // console.log(typeof(res))
        // self.$emit('getItems', ['test'])
      }).catch(err => {
        var data = [{
          GET_DATE: "2009-09-28",
          GET_NAME: "쇼핑백(황토색바지) 010)6799-****",
          GET_POSITION: "신명운수",
          ID: 15955111,
          IMAGE_URL: "",
          TAKE_PLACE: "회사내 분실센터",
        }, {
          GET_DATE: "2009-09-28",
          GET_NAME: "쇼핑백(황토색바지) 010)6799-****",
          GET_POSITION: "신명운수",
          ID: 15955111,
          IMAGE_URL: "",
          TAKE_PLACE: "회사내 분실센터",
        }, {
          GET_DATE: "2009-09-28",
          GET_NAME: "쇼핑백(황토색바지) 010)6799-****",
          GET_POSITION: "신명운수",
          ID: 15955111,
          IMAGE_URL: "",
          TAKE_PLACE: "회사내 분실센터",
        }, {
          GET_DATE: "2009-09-28",
          GET_NAME: "쇼핑백(황토색바지) 010)6799-****",
          GET_POSITION: "신명운수",
          ID: 15955111,
          IMAGE_URL: "",
          TAKE_PLACE: "회사내 분실센터",
        }, {
          GET_DATE: "2009-09-28",
          GET_NAME: "쇼핑백(황토색바지) 010)6799-****",
          GET_POSITION: "신명운수",
          ID: 15955111,
          IMAGE_URL: "",
          TAKE_PLACE: "회사내 분실센터",
        }]
        this.$emit('getItems', data)
        // alert('문제가 발생했습니다.')
      })
    }
  }
};
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
  cursor: pointer;
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
.select.selected span {
  color: #333;
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
  padding-left: 20px;
  box-sizing: border-box;
  font-size: 16px;
}
.lost-date {
  width: 218px;
  height: 56px;
  border-radius: 5px;
  background-color: #ffffff;
  border: solid 1px #dcdcdc;
  padding-left: 20px;
  box-sizing: border-box;
  font-size: 16px;
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
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
#options .optionItem {
  height: 120px;
  width: 120px;
  cursor: pointer;
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
