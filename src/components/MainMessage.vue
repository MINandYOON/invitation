<template>
  <p>
    안녕하세요 대충 얼마만큼의 길이가 적당할지 몰라서 <br />
    아무말이나 적어봅니다. 대충 이정도 적었으면 얼마나<br />
    적었으면 얼마나 될런지 궁금하네요 끼룩끼룩 <br />
    한줄을 더 써야 그래도 좀 적당히 괜찮아 보일런지요 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
    끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 끼룩끼룩 <br />
  </p>
  <div class="main-people">
    <div>
      <div class="main-parents">
        <span>{{ groomMother }}</span>
      </div>
      의 장남 &nbsp;
      <span>{{ groomName }}</span>
    </div>
    <div>
      <div class="main-parents">
        <span>{{ brideFather }}</span>
        <span class="dot">{{ brideMother }}</span>
      </div>
      의 장녀 &nbsp;
      <span>{{ brideName }}</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'MainMessage',
  props: {
    groomName: String,
    brideName: String,
    groomMother: String,
    brideFather: String,
    brideMother: String,
  },
}
</script>
<style></style>
