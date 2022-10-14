<template>
  <div class="tesmonials">
    <h3>Testimonials</h3>
    <p>Need even more convincing?</br>Here is what our customers say about us</p>
    <div class="tests">
      <p v-if="$fetchState.pending">Fetching testimonials...</p>
      <p v-else-if="$fetchState.error">An error occurred :(</p>
      <div v-else class="testimonial-container">
        <div v-for="testimonial in testimonials.slice(currentIndex,currentIndex+itemsPerView)" class="testimonial-box">
          <p>"{{ testimonial.body }}"</p>
          <div class="user">
            <img src="~/assets/avatar-1.png" alt="avatar" />
            <div class="user-dets">
              <h5>{{ testimonial.email }}</h5>
              <p>CEO of Lorem Ipsum</p>
            </div>
          </div>
        </div>
      </div>
      <div class="nav">
        <button @click="onClickPrevious"><</button>
        <button @click="onClickNext">></button>
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
        currentIndex: 0,
        itemsPerView: 2
      }
    },
    async fetch() {
      this.testimonials = await fetch(
        'https://jsonplaceholder.typicode.com/posts/1/comments'
      ).then(res => res.json())
    },
    methods: {
      onClickNext: function () {
        if (this.currentIndex + 2 <= this.testimonials.length) {
          this.currentIndex += this.itemsPerView
        }
      },
      onClickPrevious: function () {
        if (this.currentIndex - 2 >= 0) {
          this.currentIndex -= this.itemsPerView
        }
      }
    },
    computed: {
      returnTestimonials: function () {
        return this.testimonials.slice(0,2)
      }
    },
    props: {
      logoUrls: Object
    }
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
  .tests {
      text-align: center;
  }
  .testimonial-container {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
    min-height: 430px;
  }
  .testimonial-box {
    background-color: #fff;
    padding: 40px;
    max-width: 600px;
    border-radius: 25px;
    margin-right: 50px;
    margin-left: 50px;
  }
  .testimonial-box p {
    color: #787878;
    font-size: 24px;
    margin-top: 0; 
  }
  .user {
    display: inline-block;
    margin-top: 30px;
    float: left;
  }
  .user img {
    float: left;
  }
  .user .user-dets {
    margin-left: 20px;
    float: right;
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
  .logos {
    display: flex;
    max-width: 810px;
    flex-wrap: wrap;
    justify-content: center;
    margin: auto;
    margin-top: 50px;
  }
</style>
