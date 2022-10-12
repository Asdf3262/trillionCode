<template>
  <header class="header">
    <div class="up-logo">
      <img src="~/assets/uphellas-logo.svg" alt="up-hellas" width="120px">
    </div>
    <b-container class="upper-header" fluid>
      <b-row>
        <b-col class="double">
          <img src="~/assets/5-badge.svg" alt="5-badge">
          <p id="free">HERE'S A </br>CRAZY THOUGHT</p>
          <p id="happy">Happy and healthy employees work </br>better!</p>
          <CoolButton text="FIND OUT HOW WE CAN HELP"/>
        </b-col>
        <b-col class="double">
          <img src="../assets/banner-image.png" alt="banner">
        </b-col>
      </b-row>
    </b-container>
    <p id="scroll">SCROLL FOR MORE <i class="arrow down"></i></p>
  </header>
</template>

<script>
  import CoolButton from '@/components/CoolButton'
  export default {
    name: 'AppHeader',
    components: {
      CoolButton
    }
  }
</script>
<style>
  .header {
    width: 100%;
    background-color: #ff9018;
  }
  .header .up-logo {
      text-align: center;
  }
  .header .double:first-child img {
    margin-right: 80px;
    float: right;
  }
  .header .double #happy {
    font-size: 56px;
    line-height: 70px;
  }
  .header .double #free {
    margin-top: 140px;
  }
  .header .double p {
    margin-left: 120px;
    font-size: 32px;
    color: white;
    font-weight: bold;
  }
  .header .double img {
    max-width: 49vw;
  }

  .header #scroll {
    text-align: center;
    font-size: 14px;
    font-weight: bold;
    color: rgb(67,62,65);
    margin-bottom: 0px;
  }
  .arrow {
    display: block;
    width: 5px;
    margin: auto;
    border: solid black;
    border-width: 0 3px 3px 0;
    padding: 3px;
  }
  .down {
    transform: rotate(45deg);
    -webkit-transform: rotate(45deg);
  }
</style>
