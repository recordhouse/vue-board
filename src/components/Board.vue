<template>
  <div class="board-wrap">

    <!-- 검색창 -->
    <div class="input-text-wrap">
      <input type="text" class="input-text-form" />
      <button type="button" class="input-search-btn">검색</button>
    </div>

    <div class="content-wrap">

      <div class="content-box">

        <div class="table-box">

          <div class="table-top">
            <h2 class="table-title">사용자 정보</h2>
            <button class="table-title-btn">사용자 정보 수정</button>
          </div>

          <table class="table">
            <tr>
              <td>이름</td>
              <td>연락처</td>
              <td>주소</td>
              <td>이메일</td>
              <td>특이사항</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
            </tr>
          </table>
        </div>
        <div class="table-box">
          <div class="table-top">
            <h2 class="table-title">서비스 내역</h2>
          </div>
          <table class="table">
            <tr>
              <td>아파트 이름</td>
              <td>날짜</td>
              <td>주소</td>
              <td>주택점검</td>
              <td>결제필요</td>
              <td>결제인증</td>
              <td>예약확정</td>
              <td>특이사항</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
            </tr>
          </table>
        </div>
        <div class="table-box">
          <div class="table-top">
            <h2 class="table-title">상담내역</h2>
          </div>
          <table class="table">
            <tr>
              <td>날짜</td>
              <td>고객 행동</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
            </tr>
            <tr>
              <td>-</td>
              <td>-</td>
            </tr>
          </table>
        </div>
      </div>


      <div class="content-box">
        <!-- <div class="tap-btn-wrap">
          <button type="button">서비스 내역</button>
          <button type="button">상담내역</button>
        </div>
        <div class="tap-content-wrap">

        </div> -->

      </div>

    </div>

    <!-- <h1>{{ msg }}</h1> -->
  </div>
</template>



<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>


<style scoped>
.board-wrap {
  padding: 20px;
}

.input-text-wrap {
  position: relative;
  box-sizing: border-box;
  padding-right: 80px;
}

.input-text-wrap .input-text-form {
  box-sizing: border-box;
  width: 100%;
  height: 30px;
}

.input-text-wrap .input-search-btn {
  position: absolute;
  top: 0;
  right: 0;
  width: 75px;
  height: 30px;
}

.content-wrap {
  margin-top: 20px;
}
.content-wrap::after {
  content: '';
  display: block;
  clear: both;
}

.content-wrap .content-box {
  float: left;
  width: 50%;
}

.table-box {
  position: relative;
  margin-top: 20px;
}

.table-box .table-title {
  font-size: 20px;
}

.table-box .table-title-btn {
  position: absolute;
  top: 0;
  right: 0;
  height: 30px;
}

.table-box .table {
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
  border-spacing: 0;
  width: 100%;
}

.table-box .table td {
  border-left: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
  padding: 5px 10px;
}

.table-box .table td:last-child {
  border-right: 1px solid #ccc;
}

.table-box .table tr:last-child td {
  border-bottom: none;
}
</style>
