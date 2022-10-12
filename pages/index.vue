<template>
  <div class="wrapper">
    <AppHeader/>
    <AppMain/>
  </div>
</template>

<script>
  import AppMain from '@/components/AppMain'
  import AppHeader from '@/components/AppHeader'
  export default {
    name: 'IndexPage',
    components: {
      AppHeader,
      AppMain
    }
  }
</script>
