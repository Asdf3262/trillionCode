<template>
  <header class="header">
    <div class="up-logo">
      <img src="~/assets/uphellas-logo.svg" alt="up-hellas" width="120px">
    </div>
    <b-container class="upper-header" fluid>
      <b-row>
        <b-col class="double" cols="12" md="12" xl="6">
          <img src="~/assets/5-badge.svg" alt="5-badge">
          <p id="free">HERE'S A </br>CRAZY THOUGHT</p>
          <p id="happy">Happy and healthy employees work </br>better!</p>
          <CoolButton parents="1" goTo="endOfHeader" text="FIND OUT HOW WE CAN HELP"/>
        </b-col>
        <b-col class="double" md="12" xl="6">
          <img src="../assets/banner-image.png" alt="banner">
        </b-col>
      </b-row>
    </b-container>
    <p ref="endOfHeader" id="scroll">SCROLL FOR MORE <i class="arrow down"></i></p>
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
  .upper-header {
    max-width: 1920px;
  }
  .header .up-logo {
    text-align: center;
  }
  .header .double {
    padding: 0;
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
    font-family: "FreeScript";
    color: #00c8ff;
    text-shadow: -5px 2px #7a4e1f;
    transform: rotate(-6deg);
    margin-left: 95px;
    display: inline-block;
    text-align: left;
    letter-spacing: 2px;
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
  @media only screen and (max-width: 1200px) {
    .header .double img {
      max-width: 100%;
      margin-top: 30px;
    }
    .header .double:nth-child(2) {
      text-align: center;
    }
  }
  @media only screen and (max-width: 991px) {

    .header .double p {
      margin-left: 20px;
      margin-right: 20px;
    }

    .header .double #free {
      margin-top: 20px;
    }
  }
</style>
