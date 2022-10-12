<template>
  <main>
    <h3>Happy & healthy employees work better</h3>
    <p>We are Up. We design and deliver digital-first employee benefits that transform the workplace experience.</p>
    <CoolBox imagesrc="~/assets/go-for-eat.svg"/>
  </main>
</template>

<script>
  import CoolBox from '@/components/CoolBox'
  export default {
    components: {
      CoolBox
    }
  }
</script>

<style>
  main {
    padding-top: 160px;
    background-color: #ff9018;
  }
  h3, p {
    text-align: center;
  }
  h3 {
    color: white;
    font-size: 46px;
  }
  p {
    color: #ffebd7;
    font-size: 24px;
    margin-top: 20px;
  }
</style>
