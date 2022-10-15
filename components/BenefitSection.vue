<template>
  <div :class="'benefits' + alignment">
    <h3 class="title">{{ title }}</h3>
    <div class="details">
      <img :src="boxImage" alt="svg" />
      <p class="card">{{ card }}</p>
      <h4>{{ boxTitle }}</h4>
      <p class="intro">{{ intro }}</p>
      <p class="tax">{{ taxes }}</p>
      <h5>BENEFITS</h5>
      <ul>
        <li v-for="item in items">
          {{ item.message }}
        </li>
      </ul>
      <div class="contact">
        <CoolButton :text="btn" goTo="contact" parents="2"/>
      </div>
    </div>
    <div class="benefits-bg">
      <img :src="bgImage"/>
    </div>
  </div>
</template>

<script>
  import CoolButton from '@/components/CoolButton'
  export default {
    props: {
      title: String,
      card: String,
      intro: String,
      taxes: String,
      boxTitle: String,
      boxImage: String,
      bgImage: String,
      alignment: String,
      btn: String,
      items: Array
    },
    components: {
      CoolButton
    }
  }
</script>

<style>
  .benefits {
    padding-top: 100px;
    padding-bottom: 80px;
    position: relative;
  }
  .left {
    background-color: #f9bb32;
  }
  .left .benefits-bg {
    right: 0;
  }
  .right {
    background-color: #ee5a5a;
  }
  .right h3 {
    margin-left: auto;
    margin-right: 5px;
  }
  .right .details {
    margin-left: auto;
    margin-right: 120px;
  }
  .left button.cool {
    background-color: #fd9e19;
  }
  .right button.cool {
    background-color: #ee5a5a;
  }
  .title {
    font-family: "FreeScript";
    color: #00c8ff;
    text-shadow: -5px 2px #7a4e1f;
    transform: rotate(-5deg);
    max-width: 500px;
    text-align: left;
    margin-left: 120px;
    margin-bottom: 30px;
  }
  .details {
    max-width: 800px;
    position: relative;
    padding-bottom: 70px;
    background-color: #fff;
    border: 8px solid rgb(48,54,68);
    border-radius: 50px;
    border-top: 4px solid rgb(48,54,68);
    border-right: 4px solid rgb(48,54,68);
    padding-left: 40px;
    padding-right: 40px;
    padding-top: 20px;
    margin-left: 120px;
    z-index: 1;
  }
  .details p, .details h4, .details h5 {
    color: #303644;
  }
  .details h4 {
    margin-top: 40px;
    font-weight: bold;
    font-size: 38px;
    max-width: 540px;
  }
  .details .intro {
    font-size: 18px;
    text-align: left;
    margin-bottom: 0;
  }
  .details .card {
    background-color: #fd9e19;
    border-radius: 30px;
    display: inline-block;
    color: #fff;
    padding: 0 10px 0 10px;
    font-size: 14px;
    font-weight: bold;
    margin-left: 40px;
  }
  .tax {
    background-color: #f0f0f0;
    font-size: 14px;
    text-align: left;
    padding: 10px;
    font-weight: bold;
    border-radius: 12px;
    display: inline-block;
  }
  .details h5 {
    font-weight: bold;
    font-size: 18px;
  }
  .details ul {
    list-style: none;
    padding-left: 20px;
    margin-top: 20px;
  }
  .details ul li {
    margin-bottom: 15px;
    font-weight: bold;
    color: #303644d4;
  }
  .details ul li:before {
    content: '✓';
    color: #03c9ff;
    margin-right: 10px;
    border: 2px solid #303644;
    border-radius: 50%;
    padding: 1px;
  }
  .details button.cool {
    color: #fff;
    text-align: right;
  }
  .details .contact {
    position: absolute;
    bottom: -8px;
    right: -4px;
  }
  .details .contact p {
    margin: 0;
  }
  .details .contact p button {
    padding-left: 40px;
    padding-right: 40px;
    border-radius: 20px 0 40px 0;
    border-right: 4px solid rgb(48,54,68);
  }
  .benefits-bg {
    position: absolute;
    top: 200px;
    top: 55%;
    transform: translateY(-50%);
  }
  .benefits-bg img {
    max-width: 600px;
  }

  @media only screen and (max-width: 991px) {
    .benefits-bg img {
        display: none;
    }
    .benefits .details {
      margin: auto;
    }
  }
</style>
