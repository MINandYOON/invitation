<template>
  <h1 class="main-title">We are getting<strong>Married</strong></h1>
  <h2 class="groom">
    신랑<strong>{{ groom }}</strong>
  </h2>
  <h2 class="bride">
    신부<strong>{{ bride }}</strong>
  </h2>
  <div class="main-bottom">
    <h3>{{ time }}</h3>
    <h4>{{ location }}</h4>
  </div>
</template>
<script>
export default {
  name: 'MainVisual',
  props: {
    groom: String,
    bride: String,
    time: String,
    location: String,
  },
}
</script>
<style></style>
