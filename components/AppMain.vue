<template>
  <main>
    <h3>Happy & healthy employees work better</h3>
    <p>We are Up. We design and deliver digital-first employee benefits that transform the workplace experience.</p>
    <b-container fluid>
      <b-row>
        <CoolBox :imagesrc="require('~/assets/go-for-eat.svg')" title="The unrivaled meal card solution"
                 :bgImage="require('~/assets/goforeat.png')" />
        <CoolBox :imagesrc="require('~/assets/UP-GIFT.svg')" title="The perfect gift"
                 :bgImage="require('~/assets/upgift.png')" />
        <CoolBox :imagesrc="require('~/assets/up-cheque.svg')" title="Where it all started; our meal vouchers"
                 :bgImage="require('~/assets/3.png')" />
        <CoolBox :imagesrc="require('~/assets/up-holidays.svg')" title="The card that takes you places"
                 :bgImage="require('~/assets/4.png')" />
        <CoolBox :imagesrc="require('~/assets/up-holidays.svg')" title="Where it all started; our meal vouchers"
                 :bgImage="require('~/assets/5.png')" />
      </b-row>
    </b-container>
    <BenefitSection title="THE UNRIVALED MEAL CARD SOLUTION" :boxImage="require('~/assets/go-for-eat.svg')"
                    card="MEAL CARD" intro="Our prepaid meal card by Mastercard is designed to offer to both our corporate
                    customers and users an umatched experience that's simple and fun" taxes="Tax exemption: 6 euros per day / 1,452
                    euros per year per employee" boxTitle="Enjoy your meals anywhere you want"/>
  </main>
</template>

<script>
  import CoolBox from '@/components/CoolBox'
  import BenefitSection from '@/components/BenefitSection'
  export default {
    components: {
      CoolBox,
      BenefitSection
    }
  }
</script>

<style>
  main {
    padding-top: 160px;
    background-color: #ff9018;
  }
  main .row {
      margin: auto;
      justify-content: center;
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
  main .container-fluid {
      max-width: 1520px;
      padding: 20px;
      margin-top: 60px;
      padding-bottom: 100px;
  }
</style>
