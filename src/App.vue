<template>
  <div id="app">
    <PageHeader/>
    <TweetData/>
  </div>
</template>

<script>
import TweetData from '@/components/TweetData.vue';
import PageHeader from '@/components/PageHeader.vue';

export default {
  name: 'App',
  components: {
    TweetData,
    PageHeader,
  }
}
</script>

<style>
html{
  background-color: lavender;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
