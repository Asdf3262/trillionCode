<template>
  <p><button @click="goto" class="cool">{{ text }}</button></p>
</template>

<script>
  export default {
    props: {
      text: String,
      styles: String,
      goTo: String,
      parents: String
    },
    methods: {
      goto() {
        if (this.goTo) {
          if (this.parents === '2') {

            var element = this.$parent.$parent.$refs[this.goTo];
            var top = element.offsetTop;

            window.scrollTo(0, top);
          }
          else {
            var element = this.$parent.$refs[this.goTo];
            var top = element.offsetTop + 120;

            window.scrollTo(0, top);
          }
        }
        else {
          console.log('No target in this button!')
        }
      }
    }
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
