<script setup>
  import {defineAsyncComponent, defineProps} from 'vue'
  import Loading from './Loading.vue'
  const props = defineProps({
    item: {
      default: {},
    },
    index: {
      type: Number
    }
  })

  const AsyncCard = defineAsyncComponent({
    loader: () => new Promise(resolve => setTimeout(() => resolve(import('./Card.vue')), (props.index + 1) * 1000)),
    loadingComponent: Loading,
    delay: 500
  })
</script>

<template>
  <AsyncCard v-bind="props.item"></AsyncCard>
</template>
