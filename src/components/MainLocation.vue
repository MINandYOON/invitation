<template>
  <span>20260201</span>
  <p>{{ time }}</p>
  <p>{{ location }}</p>
  <p>{{ address }}</p>
</template>
<script>
export default {
  name: 'MainLocation',
  props: {
    time: String,
    location: String,
    address: String,
  },
}
</script>
<style></style>
