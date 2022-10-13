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
                    euros per year per employee" boxTitle="Enjoy your meals anywhere you want" bgColor=" benefits1"
                    :bgImage="require('~/assets/goforeat.png')" btn="CONTACT US" :items="items1"/>
    <BenefitSection title="THE PERFECT GIFT" :boxImage="require('~/assets/UP-GIFT.svg')"
                    card="GIFT CARD" intro="Our reloadable gift card is the perfect gift to reward, to incentivise, to celebrate!"
                    taxes="Tax exemption: 300 euros per year per employee"
                    boxTitle="Everything you desire in a single tap" bgColor=" benefits2" :bgImage="require('~/assets/upgift.png')"
                    btn="TELL ME MORE" :items="items2"/>
    <Testimonials/>
  </main>
</template>

<script>
  import CoolBox from '@/components/CoolBox'
  import BenefitSection from '@/components/BenefitSection'
  import Testimonials from '@/components/Testimonials'
  export default {
    components: {
      CoolBox,
      BenefitSection,
      Testimonials
    },
    data() {
      return {
        items1: [
          { message: 'Order & load cards online in seconds, download invoices & reports in a click' },
          { message: 'Best in class service: Quantified & qualified with a monthly report' },
          { message: 'Our cards are accepted everywhere in Greece' },
          { message: 'Use our app for full control & mobile payments' }
        ],
        items2: [
          { message: 'Order & load cards online in seconds, download invoices & reports in a click' },
          { message: 'Buy everything you want - electronics, clothing, cosmetics and so much more' },
          { message: 'Our app is loaded with crazy-fun features' }
        ]
      }
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
  main .benefits1 {
    background-color: #f9bb32;
  }
  main .benefits1 .benefits-bg {
    right: 0;
  }
  main .benefits2 {
    background-color: #ee5a5a;
  }
  main .benefits2 h3 {
    margin-left: auto;
  }
  main .benefits2 .details {
    margin-left: auto;
    margin-right: 120px;
  }
  main .benefits1 button.cool {
    background-color: #fd9e19;
  }
  main .benefits2 button.cool {
    background-color: #ee5a5a;
  }
</style>
