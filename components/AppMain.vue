<template>
  <main>
    <h3>Happy & healthy employees work better</h3>
    <p>We are Up. We design and deliver digital-first employee benefits that transform the workplace experience.</p>
    <b-container fluid>
      <b-row class="row-cols-1 row-cols-md-2 row-cols-lg-3 row-cols-xl-5">
        <CoolBox :imagesrc="require('~/assets/go-for-eat.svg')" title="The unrivaled meal card solution"
                 :bgImage="require('~/assets/goforeat.png')" btnGoTo="up-eat" btnParents="2"/>
        <CoolBox :imagesrc="require('~/assets/UP-GIFT.svg')" title="The perfect gift"
                 :bgImage="require('~/assets/upgift.png')" btnGoTo="gift" btnParents="2"/>
        <CoolBox :imagesrc="require('~/assets/up-cheque.svg')" title="Where it all started; our meal vouchers"
                 :bgImage="require('~/assets/3.png')" />
        <CoolBox :imagesrc="require('~/assets/up-holidays.svg')" title="The card that takes you places"
                 :bgImage="require('~/assets/4.png')" />
        <CoolBox :imagesrc="require('~/assets/up-holidays.svg')" title="Where it all started; our meal vouchers"
                 :bgImage="require('~/assets/5.png')" />
      </b-row>
    </b-container>
    <div ref="up-eat">
      <BenefitSection title="THE UNRIVALED MEAL CARD SOLUTION" :boxImage="require('~/assets/go-for-eat.svg')"
                      card="MEAL CARD" intro="Our prepaid meal card by Mastercard is designed to offer to both our corporate
                    customers and users an umatched experience that's simple and fun" taxes="Tax exemption: 6 euros per day / 1,452
                    euros per year per employee" boxTitle="Enjoy your meals anywhere you want" alignment=" left"
                      :bgImage="require('~/assets/goforeat.png')" btn="CONTACT US" :items="items1" />
    </div>
    <div ref="gift">
      <BenefitSection title="THE PERFECT GIFT" :boxImage="require('~/assets/UP-GIFT.svg')"
                      card="GIFT CARD" intro="Our reloadable gift card is the perfect gift to reward, to incentivise, to celebrate!"
                      taxes="Tax exemption: 300 euros per year per employee"
                      boxTitle="Everything you desire in a single tap" alignment=" right" :bgImage="require('~/assets/upgift.png')"
                      btn="TELL ME MORE" :items="items2" />
    </div>
    <Testimonials :logoUrls="testimonialLogos"/>
    <div ref="contact">
      <ContactSection />
    </div>
  </main>
</template>

<script>
  import CoolBox from '@/components/CoolBox'
  import BenefitSection from '@/components/BenefitSection'
  import Testimonials from '@/components/Testimonials'
  import ContactSection from '@/components/ContactSection'
  export default {
    components: {
      CoolBox,
      BenefitSection,
      Testimonials,
      ContactSection
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
        ],
        testimonialLogos: [
          { imageUrl: require('~/assets/logo-1.svg') },
          { imageUrl: require('~/assets/logo-2.svg') },
          { imageUrl: require('~/assets/logo-3.svg') },
          { imageUrl: require('~/assets/logo-4.svg') },
          { imageUrl: require('~/assets/logo-5.svg') },
          { imageUrl: require('~/assets/logo-6.svg') },
          { imageUrl: require('~/assets/logo-7.svg') },
          { imageUrl: require('~/assets/logo-8.svg') }
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
  @media only screen and (max-width: 991px) {
      main {
          padding-top: 30px;
      }
  }
</style>
