<script setup>
  import CardLogic from './components/CardsLogic.vue'
  const source = [
    {
      id: 0,
      type: 'Running',
      duration: '1',
      burned: '100'
    },
    {
      id: 1,
      type: 'Jump Rope',
      duration: '1',
      burned: '400'
    },
    {
      id: 2,
      type: '',
      duration: '',
      burned: ''
    },
  ]
</script>

<template>
  <div class="Cards">
    <CardLogic :source="source" />
  </div>
</template>

<style scoped>
  .Cards {
    display: flex;
    justify-content: space-around;
    background-image: url('./assets/images/backgroundPic.jpg');
    background-size: 750px;
    background-repeat: no-repeat;
    height: 500px;
    width: 800px;
  }
</style>
