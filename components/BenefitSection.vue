<template>
  <div class="benefits">
    <h3>{{ title }}</h3>
    <div class="details">
      <img :src="boxImage" alt="svg" />
      <p>{{ card }}</p>
      <h4>{{ boxTitle }}</h4>
      <p>{{ intro }}</p>
      <p class="tax">{{ taxes }}</p>
      <h5>BENEFITS</h5>
      <ul>
        <li>Order & load cards online in seconds, download invoices & reports in a click</li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['title', 'card', 'intro', 'taxes', 'boxTitle', 'boxImage', 'bgImage']
  }
</script>
