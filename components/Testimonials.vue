<template>
  <div class="tesmonials">
    <h3>Testimonials</h3>
    <p>Need even more convincing?</br>Here is what our customers say about us</p>
    <div class="testimonial-wrapper">
      <p v-if="$fetchState.pending">Fetching testimonials...</p>
      <p v-else-if="$fetchState.error">An error occurred :(</p>
      <div v-else class="testimonial-container">
        <b-container>
          <b-row>
            <div v-for="testimonial in testimonials" class="col-sm-12 col-xl-6 ">
              <div class="testimonial-box">
                <p>"{{ testimonial.body }}"</p>
                <div class="user">
                  <img src="~/assets/avatar-1.png" alt="avatar" />
                  <div class="user-dets">
                    <h5>User ID: {{ testimonial.userId }}</h5>
                    <p>CEO of Lorem Ipsum</p>
                  </div>
                </div>
              </div>
            </div>
          </b-row>
        </b-container>
      </div>
      <div class="nav">
        <button @click="onClickPrevious" :class="isBottomLimit()"><</button>
        <button @click="onClickNext" :class="isTopLimit()">></button>
      </div>
    </div>
    <div class="logos">
      <div v-for="logoUrl in logoUrls">
        <img :src="logoUrl.imageUrl" alt="a"/>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        testimonials: [],
        currentPage: 1,
        itemsPerView: 2
      }
    },
    async fetch() {
      this.testimonials = await fetch(
        'https://jsonplaceholder.typicode.com/posts/?_page=' + this.currentPage + '&_limit=' + this.itemsPerView
      ).then(res => res.json())
    },
    methods: {
      onClickNext: function () {
        if (this.currentPage < 50) {
          this.currentPage += 1
        }
      },
      onClickPrevious: function () {
        if (this.currentPage > 1) {
          this.currentPage -= 1
        }
      },
      isTopLimit: function () {
        if ( this.currentPage == 50) {
          return 'limit';
        }
      },
      isBottomLimit: function () {
        if (this.currentPage == 1) {
          return 'limit';
        }
      }
    },
    props: {
      logoUrls: Array
    },
    watch: {
      'currentPage': '$fetch'
    },
  }
</script>

<style scoped>
  .tesmonials {
    padding-top: 80px;
    padding-bottom: 50px;
    background-color: #ffd069;
  }
  h3 {
    color: #303644;
    font-weight: bold;
    letter-spacing: 1px;
  }
  p {
    color: #58534b;
    font-size: 18px;
    letter-spacing: 1px;
  }
  .testimonial-wrapper {
    text-align: center;
    min-height: 505px;
    padding-top: 20px;
  }
  .testimonial-container {
    margin-bottom: 20px;
    min-height: 430px;
  }
  .testimonial-box {
    background-color: #fff;
    padding: 40px;
    border-radius: 25px;
    margin-bottom: 20px;
  }
  .testimonial-box p {
    color: #787878;
    font-size: 24px;
    margin-top: 0; 
  }
  .user {
    display: block;
    margin-top: 30px;
  }
  .user img {
    float: left;
  }
  .user .user-dets {
    margin-left: 85px;
    padding-top: 8px;
  }
  .user h5 {
      text-align: left;
  }
  .user p {
    font-size: 16px;
    text-align: left;
  }
  .nav {
    display: inherit;
    text-align: center;
  }
  .nav button {
    border: 2px solid #fff;
    border-radius: 20px;
    background-color: #ff2020;
    color: #fff;
    font-size: 20px;
    padding: 10px;
  }
  .nav .limit {
      display: none;
  }
  .logos {
    display: flex;
    max-width: 810px;
    flex-wrap: wrap;
    justify-content: center;
    margin: auto;
    margin-top: 50px;
  }
</style>
