<template>
  
  <div id="card">
    <!-- <embed src="../assets/logo_header.svg" /> -->
    <!-- <link rel="stylesheet" href="//cdn.rawgit.com/hiun/NanumSquare/master/nanumsquare.css" type='text/css'> -->
    <!-- <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Nanum Gothic Coding"> -->
    <div id="img-wrapper">
      <img id="picture" src="../assets/icon_picture.png" />
      <div id="plus">
        <img id="plus-icon" src="../assets/bt_plus.png" />
      </div>
    </div>




    <p id="name">닥스 벨트3종류</p>
    <span id="code">50355809</span>
    <table>
      <tr>
        <td class="col1">
          <span class="text-size">습득장소</span>
        </td>
        <td class="col2">
          <span class="text-size">버스</span>
        </td>
      </tr>
      <tr>
        <td class="col1">
          <span class="text-size">보관장소</span>
        </td>
        <td class="col2">
          <span class="text-size">유스퀘어 유실물센터</span>
        </td>
      </tr>
      <tr>
        <td class="col1">
          <span class="text-size">습득일</span>
        </td>
        <td class="col2">
          <span class="text-size">2018.05.06</span>
        </td>
      </tr>
    </table>

    <button id="bottom"><span class="text-size">보러가기</span></button>

  </div>

</template>

<script>
export default {
  name: 'Card',
  data () {
    return {

    }
  }
}

</script>


<style scoped>
@import url(https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css);

#card {
  width: 280px;
  height: 486px;
  background-color: white;
  border: 1px solid #000000;
  text-align: left;
  font-family: 'NanumSquare';
}

#img-wrapper {
  width: 250px;
  height: 250px;
  background-color: #c3d4ea;
  margin-top: 15px;
  margin-left: 15px;
  z-index: 10;
}

#picture {
  z-index: 100;
  margin-top: 78px;
  margin-left: 60px;
}

#plus-icon {
  margin: 7px;
  width: 26px;
  height: 26px;
}

#plus {
  width: 40px;
  height: 40px;
  float: right;
  background-color: #606a76;
  margin-top: 210px;
}

#name {
  font-size: 22.5px;
  color: #333333;
  margin-left: 15px;
  margin-top: 15px;
  margin-bottom: 5px;
}

#code {
  color: #989898;
  font-size: 13px;
  margin-left: 15px;
  margin-top: 10px;
}

table{
  margin-left: 15px;
  margin-top: 19px;
  margin-bottom: 24px;
  font-size: 13px;
}

.col1 {
  height: 14px;
  font-size: 13px;
  color: #989898;
  text-align: left;
  width: 73px;
  font-size: 13px;
}

.col2 {
  font-size: 13px;
  color: #333333;
}

#bottom {
  width: 168px;
  height: 32px;
  border-radius: 16px;
  background-color: #ffffff;
  border: solid 1px #0a52b3;
  color: #0a52b3;
  font-size: 13px;
  text-align: center;
  margin-left: 56px;
  margin-bottom: 27px;
  font-size: 13px;
}

#bottom:hover {
  background-color: #0a52b3;
  color: #ffffff;
}

</style>
