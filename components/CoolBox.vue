<template>
  <b-col class="thecoolbox" xl="3">
    <img :src="imagesrc" alt="svg" />
    <p>{{ title }}</p>
    <img :src="bgImage" alt="png" />
    <div class="learnMoreBtn">
      <CoolButton text="LEARN MORE" :parents="btnParents" :goTo="btnGoTo"/>
    </div>
  </b-col>
</template>

<script>
  import CoolButton from '@/components/CoolButton'
  export default {
    components: {
      CoolButton
    },
    props: {
      imagesrc: String,
      title: String,
      bgImage: String,
      btnParents: String,
      btnGoTo: String
     }
  }
</script>

<style>
  .thecoolbox {
    max-width: 280px;
    text-align: center;
    background-color: #ffc98f;
    border: 4px solid rgb(48,54,68);
    border-radius: 50px;
    box-sizing: border-box;
    height: 475px;
    padding-top: 20px;
    transition: border 0.1s linear;
    position: relative;
    padding-left: 5px;
    padding-right: 5px;
    margin-right: 15px;
    margin-bottom: 20px;
  }
  .thecoolbox:hover {
    border: 8px solid rgb(48,54,68);
    border-top: 4px solid rgb(48,54,68);
    border-right: 4px solid rgb(48,54,68);
  }
  .thecoolbox img {
    width: 100%;
  }
  .thecoolbox img:first-child {
    width: 75%;
  }
  .thecoolbox p {
    font-size: 18px;
    padding: 5px;
    margin: 0;
  }
  .thecoolbox .learnMoreBtn p {
    padding-bottom: 0;
  }
  .thecoolbox .learnMoreBtn {
    position: absolute;
    opacity: 0;
    visibility: hidden;
    bottom: -4px;
    left: 0;
    right: 0;
    transition: all 0.4s linear;
    margin-bottom: 10px;
  }
  .thecoolbox:hover .learnMoreBtn {
    opacity: 1;
    visibility: visible;
    margin-bottom: 0;
  }
  .thecoolbox button.cool {
    border-radius: 20px 20px 0 0;
    padding: 8px 30px 8px 30px;
    background-color: #ffce3c;
    border-width: 4px;
    font-size: 14px;
  }
</style>
