<template>
  <div class="board-wrap">

    <!-- 검색창 -->
    <div class="input-search-wrap">
      <input type="text" class="input-search-form" />
      <button type="button" class="input-search-btn">검색</button>
    </div>

    <div class="content-wrap">
      <div class="content-box left">

        <div class="table-box">
          <div class="table-top">
            <h2 class="table-title">사용자 정보</h2>
            <button class="table-title-btn">사용자 정보 수정</button>
          </div>

          <table class="table">
            <colgroup>
              <col span="5" width="20%">
            </colgroup>
            <thead>
              <tr>
                <td>이름</td>
                <td>연락처</td>
                <td>주소</td>
                <td>이메일</td>
                <td>특이사항</td>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in userData" v-bind:key="item">
                <td>{{ item.name }}</td>
                <td>{{ item.contact }}</td>
                <td>{{ item.address }}</td>
                <td>{{ item.email }}</td>
                <td>{{ item.info }}</td>
              </tr>
            </tbody>
          </table>
        </div>

        <div class="table-box">
          <div class="table-top">
            <h2 class="table-title">서비스 내역</h2>
          </div>
          <table class="table">
            <colgroup>
              <col span="7" width="10%">
              <col width="*">
            </colgroup>
            <thead>
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
            </thead>
            <tbody>
              <tr v-for="item in serviceData" v-bind:key="item">
                <td>{{ item.aptName }}</td>
                <td>{{ item.date }}</td>
                <td>{{ item.address }}</td>
                <td>{{ item.check }}</td>
                <td>{{ item.payment }}</td>
                <td>{{ item.certification }}</td>
                <td>{{ item.reserve }}</td>
                <td>{{ item.info }}</td>
              </tr>
            </tbody>
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

      <div class="content-box right">
        <div class="tab-wrap">
          <div class="tab-btn">
            <button type="button" class="on">서비스 내역</button>
            <button type="button">상담내역</button>
          </div>
          <div class="tab-content">

            <div class="input-text">
              <label for="input-text01">아파트 이름</label>
              <input type="text" id="input-text01" v-model="serviceInputData.aptName" />
            </div>
            <div class="input-text">
              <label for="input-text02">날짜</label>
              <input type="text" id="input-text02" v-model="serviceInputData.date" />
            </div>

            <div class="input-text">
              <label for="input-text03">주소</label>
              <input type="text" id="input-text03" v-model="serviceInputData.address" />
            </div>

            <div class="input-text">
              <label for="input-text04">주택점검</label>
              <input type="text" id="input-text04" v-model="serviceInputData.check" />
            </div>

            <div class="input-text">
              <label for="input-text05">결제필요</label>
              <input type="text" id="input-text05" v-model="serviceInputData.payment" />
            </div>
            <div class="input-text">
              <label for="input-text06">결제인증</label>
              <input type="text" id="input-text06" v-model="serviceInputData.certification" />
            </div>
            <div class="input-text">
              <label for="input-text07">예약확정</label>
              <input type="text" id="input-text07" v-model="serviceInputData.reserve" />
            </div>

            <div class="input-text">
              <label for="input-text08">특이사항</label>
              <input type="text" id="input-text08" v-model="serviceInputData.info" />
            </div>

            <!-- <textarea class="textarea"></textarea> -->

            <button type="button" class="tab-content-btn" @click="tabContentBtnClick">등록</button>

          </div>
        </div>
      </div>
    </div>

    <!-- <h1>{{ msg }}</h1> -->
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      userData: [
        {
          name: '가가가',
          contact: '01012345678',
          address: '서울시 강남구 논현동',
          email: 'aaa@naver.com',
          info: '특이사항은 블라블라'
        },
        {
          name: '나나나',
          contact: '01012345678',
          address: '서울시 강남구 논현동',
          email: 'bbb@naver.com',
          info: '특이사항은 블라블라'
        },
        {
          name: '다다다',
          contact: '01012345678',
          address: '서울시 강남구 논현동',
          email: 'ccc@naver.com',
          info: '특이사항은 블라블라'
        }
      ],
      serviceData:
      [

      ],
      serviceInputData:
      {
        aptName: '',
        date: '',
        address: '',
        check: '',
        payment: '',
        certification: '',
        reserve: '',
        info: '',
      }
    }
  },
  methods: {
    // 우측 등록 버튼 클릭
    tabContentBtnClick() {


      this.serviceData.push({...this.serviceInputData});

      console.log(this.serviceData);

    }
  },
  mounted() {
    console.log(this.userData)
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>
.board-wrap {
  padding: 20px;
}

.input-search-wrap {
  position: relative;
  box-sizing: border-box;
  padding-right: 80px;
}

.input-search-wrap .input-search-form {
  box-sizing: border-box;
  width: 100%;
  height: 40px;
}

.input-search-wrap .input-search-btn {
  position: absolute;
  top: 0;
  right: 0;
  width: 75px;
  height: 40px;
  border: 1px solid #999;
  background-color: #e0e0e0;
  cursor: pointer;
}

.content-wrap {
  margin-top: 20px;
}

.content-wrap::after {
  content: '';
  display: block;
  clear: both;
}

.content-wrap .content-box.left {
  float: left;
  width: 67%;
}

.content-wrap .content-box.right {
  float: right;
  width: 30%;
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
  border: 1px solid #999;
  background-color: #e0e0e0;
  cursor: pointer;
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

.table-box .table tbody tr:last-child td {
  border-bottom: none;
}

.tab-wrap {
  margin-top: 20px;
}

.tab-wrap .tab-btn>button {
  width: 50%;
  height: 35px;
  border: 1px solid #999;
  background-color: #f0f0f0;
  cursor: pointer;
}

.tab-wrap .tab-btn>button:hover {
  background: #e0e0e0;
}

.tab-wrap .tab-btn>button.on {
  background: #ccc;
}

.tab-wrap .tab-content {
  margin-top: 10px;
}

.tab-wrap .tab-content .textarea {
  padding: 0;
  box-sizing: border-box;
  width: 100%;
  height: 200px;
  resize: none;
}

.tab-wrap .tab-content .tab-content-btn {
  margin-top: 20px;
  width: 100%;
  height: 35px;
  border: 1px solid #999;
  background-color: #f0f0f0;
  cursor: pointer;
}

.input-text {
  position: relative;
  margin-top: 10px;
  padding-left: 100px;
}

.input-text>label {
  position: absolute;
  top: 3px;
  left: 0;
}

.input-text>input[type=text] {
  box-sizing: border-box;
  width: 100%;
  height: 30px;
}
</style>
