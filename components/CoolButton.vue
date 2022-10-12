<template>
  <p><button class="cool">{{ text }}</button></p>
</template>

<script>
  export default {
    props: ['text', 'styles']
  }
</script>

<style>
  p button.cool {
    border: 8px solid rgb(48,54,68);
    border-radius: 50px;
    border-top: 2px solid rgb(48,54,68);
    border-right: 2px solid rgb(48,54,68);
    padding: 15px;
    padding-left: 20px;
    padding-right: 20px;
    font-size: 16px;
    font-weight: bold;
    color: rgb(48,54,68);
  }
</style>
