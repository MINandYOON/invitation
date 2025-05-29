<template>
  <h5>마음 전하실 곳</h5>
  <div class="main-account-list main-account-groom">
    <button @click="toggleGroom" :class="{ close: groomClosed }">신랑측 계좌번호 확인하기</button>
    <ul :class="{ close: groomClosed }">
      <li v-for="(item, index) in groomAccount" :key="index">
        <div>
          <strong>{{ item.name }}</strong>
          <p>
            <b>{{ item.bank }}</b> {{ item.number }}
          </p>
        </div>
        <button @click="copyGroom(index)">
          <i class="icon-copy"></i> {{ copiedGroom[index] ? '복사완료' : '계좌번호 복사' }}
        </button>
      </li>
    </ul>
  </div>
  <div class="main-account-list main-account-bride">
    <button @click="toggleBride" :class="{ close: brideClosed }">신부측 계좌번호 확인하기</button>
    <ul :class="{ close: brideClosed }">
      <li v-for="(item, index) in brideAccount" :key="index">
        <div>
          <strong>{{ item.name }}</strong>
          <p>
            <b>{{ item.bank }}</b> {{ item.number }}
          </p>
        </div>
        <button @click="copyBride(index)">
          <i class="icon-copy"></i> {{ copiedBride[index] ? '복사완료' : '계좌번호 복사' }}
        </button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'MainAccout',
  props: {
    groomAccount: Array,
    brideAccount: Array,
    toggleBride: Function,
    toggleGroom: Function,
    copiedGroom: Array,
    copiedBride: Array,
    copyGroom: Function,
    copyBride: Function,
    groomClosed: Boolean,
    brideClosed: Boolean,
  },
}
</script>
