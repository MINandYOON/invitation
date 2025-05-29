<template>
  <h5>오시는 길</h5>
  <strong>{{ location }} 35층</strong>
  <p>{{ address }}</p>
  <div id="map" style="width: 100%; height: 300px; background: #999; margin-top: 2rem"></div>
  <div class="main-map-nav">
    <a href="https://naver.me/5r9z4Z05"><i class="icon-naver"></i>네이버지도</a>
    <a href="kakaomap://look?p=37.536496586701034,127.13222653861892"
      ><i class="icon-kakao"></i>카카오지도</a
    >
  </div>
  <div class="main-map-trans">
    <div>
      <span>지하철</span>
      <p>5호선 강동역 1번 출구 연결</p>
    </div>
    <div>
      <span>버스</span>
      <p>지선&nbsp;&nbsp;3214 3316</p>
      <p>간선&nbsp;&nbsp;130 341 342 370</p>
      <p>일반&nbsp;&nbsp;1-4 23 30-3 112 112-1 112-5</p>
      <p>직행&nbsp;&nbsp;1113 1113-1 1113-2 1113-11 9301</p>
    </div>
    <div>
      <span>주차</span>
      <p>"이스트 센트럴 타워 주차장"으로 검색 후 오피스 방면으로 출입하면 됩니다.</p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'MainMap',
  props: {
    location: String,
    address: String,
  },
}
</script>
