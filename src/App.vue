<template>
  <div class="wrap">
    <section>
      <!-- 비주얼 -->
      <article class="main-visual">
        <MainVisual :groom="groom" :bride="bride" :time="time" :location="location"></MainVisual>
      </article>
      <!-- 장소 -->
      <article class="main-word">
        <MainLocation :time="time" :location="location" :address="address"></MainLocation>
      </article>
      <!-- 드리는 말씀 -->
      <article class="main-message">
        <MainMessage
          :groomName="groomName"
          :brideName="brideName"
          :groomMother="groomMother"
          :brideFather="brideFather"
          :brideMother="brideMother"
        ></MainMessage>
      </article>
      <!-- 달력 -->
      <article class="main-calendar">
        <h5>예식 일시</h5>
        <strong>{{ time }}</strong>
        <p>{{ location }}</p>
        <MainCalendar></MainCalendar>
      </article>
      <!-- 오시는 길 -->
      <article class="main-map">
        <MainMap :location="location" :address="address"></MainMap>
      </article>
      <!-- 갤러리 -->
      <article class="main-gallery">
        <MainGallery galleryID="my-gallery-grid" :images="images"></MainGallery>
      </article>
      <!-- 마음 전하실 곳 -->
      <article class="main-account">
        <MainAccount
          :groomAccount="groomAccount"
          :brideAccount="brideAccount"
          :toggleBride="toggleBride"
          :toggleGroom="toggleGroom"
          :copyGroom="copyGroom"
          :copyBride="copyBride"
          :copiedGroom="copiedGroom"
          :copiedBride="copiedBride"
          :groomClosed="groomClosed"
          :brideClosed="brideClosed"
        ></MainAccount>
      </article>
      <!-- 마치는 말 -->
      <article class="main-closing">
        <p>
          항상 저희를 지지해주시고 믿어주신 부모님, <br />
          그리고 응원과 축하의 마음을 아낌없이 전해주신 <br />
          모든 분들에게 진심으로 감사드립니다.
        </p>
        <button @click="sendkakao">카카오톡 공유하기</button>
      </article>
    </section>
    <footer>
      <p>All rights reserved by JEONG YOON.</p>
      <p>Developed it and Designed it by JEONG YOON</p>
    </footer>
  </div>
</template>

<script>
import MainCalendar from './components/MainCalendar.vue'
import MainGallery from './components/MainGallery.vue'
import GalleryItems from './assets/data/images'
import GroomAccount from './assets/data/groomAccount'
import BrideAccount from './assets/data/brideAccount'
import MainMessage from './components/MainMessage.vue'
import MainVisual from './components/MainVisual.vue'
import MainLocation from './components/MainLocation.vue'
import MainMap from './components/MainMap.vue'
import MainAccount from './components/MainAccount.vue'

export default {
  components: {
    MainCalendar: MainCalendar,
    MainGallery: MainGallery,
    MainMessage: MainMessage,
    MainVisual: MainVisual,
    MainLocation: MainLocation,
    MainMap: MainMap,
    MainAccount: MainAccount,
  },
  name: 'MapView',

  data() {
    return {
      groom: '김뫄뫄',
      bride: '김뭐뭐',
      groomName: '뫄뫄',
      brideName: '뭐뭐',
      groomFather: '김와와',
      groomMother: '박와와',
      brideFather: '김와와',
      brideMother: '최와와',
      location: '강동 루벨 웨딩홀',
      address: '서울특별시 강동구 천호대로 1077',
      time: '2026.02.01 일요일 15:30',
      map: null,
      images: GalleryItems,
      groomClosed: false,
      brideClosed: false,
      groomAccount: GroomAccount,
      brideAccount: BrideAccount,
      copiedGroom: [],
      copiedBride: [],
    }
  },

  mounted() {
    this.copiedGroom = this.groomAccount.map(() => false)
    this.copiedBride = this.brideAccount.map(() => false)
    window.kakao.maps.load(() => {
      const container = document.getElementById('map')

      const options = {
        center: new window.kakao.maps.LatLng(37.5365319, 127.1323567),
        level: 3,
      }

      const map = new window.kakao.maps.Map(container, options)

      const imageSrc = '/img/mark-heart.svg'
      const imageSize = new window.kakao.maps.Size(40, 40)
      const imageOption = { offset: new window.kakao.maps.Point(20, 40) }

      const markerImage = new window.kakao.maps.MarkerImage(imageSrc, imageSize, imageOption)

      const markerPosition = new window.kakao.maps.LatLng(37.5365319, 127.1323567)

      const marker = new window.kakao.maps.Marker({
        position: markerPosition,
        image: markerImage,
        title: '예식장',
      })

      marker.setMap(map)

      // ✅ 항상 보이는 커스텀 오버레이
      const overlayContent = `
    <div class="customoverlay">
      <div class="custom-box">
        <strong>강동 루벨 웨딩홀</strong>
      </div>
    </div>
  `

      const customOverlay = new window.kakao.maps.CustomOverlay({
        position: markerPosition,
        content: overlayContent,
        yAnchor: 1, // 마커 위에 위치하도록 설정
      })

      customOverlay.setMap(map) // 항상 보이게 설정
    })
  },

  methods: {
    toggleGroom() {
      this.groomClosed = !this.groomClosed
    },

    toggleBride() {
      this.brideClosed = !this.brideClosed
    },

    copyGroom(index) {
      const text = this.groomAccount[index].number
      navigator.clipboard
        .writeText(text)
        .then(() => {
          this.copiedGroom[index] = true
          setTimeout(() => {
            this.copiedGroom[index] = false
          }, 2000)
        })
        .catch(() => {
          alert('복사에 실패했습니다.')
        })
    },

    copyBride(index) {
      const text = this.brideAccount[index].number
      navigator.clipboard
        .writeText(text)
        .then(() => {
          this.copiedBride[index] = true
          setTimeout(() => {
            this.copiedBride[index] = false
          }, 2000)
        })
        .catch(() => {
          alert('복사에 실패했습니다.')
        })
    },

    sendkakao() {
      if (!window.Kakao) {
        alert('Kakao SDK not loaded')
        return
      }
      if (!window.Kakao.isInitialized()) {
        window.Kakao.init('f113a89e60f4665ff24f9a01eb2dd919')
      }

      window.Kakao.Link.sendDefault({
        objectType: 'text',
        text: '뫄뫄와 뭐뭐의 결혼식에 초대합니다!',
        link: {
          mobileWebUrl: 'https://minandyoon.github.io/',
          webUrl: 'https://minandyoon.github.io/',
        },
      })
    },
  },
}
</script>

<style></style>
