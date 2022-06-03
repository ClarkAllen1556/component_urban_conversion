<template>
  <h1>Hello {{ name }}</h1>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      name: 'I like pizza',
    };
  },
});
</script>
