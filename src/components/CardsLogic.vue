<script setup>
  import { defineProps, defineAsyncComponent } from 'vue'
  import CardWithLazyLoad from './CardWithLazyLoad.vue'
  const props = defineProps({
    source: {
      type: Array,
      default: []
    }
  })


</script>

<template>
  <CardWithLazyLoad 
    v-for="(item, index) in props.source" 
    :key="item.id"
    :index="index"
    :item="item"
  ></CardWithLazyLoad>
</template>
