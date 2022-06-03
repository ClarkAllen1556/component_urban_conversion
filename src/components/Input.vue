<script setup>
defineProps({
  placeHolder: {
    type: String,
  },
  value: {
    type: String,
  },
  type: {
    type: String,
    default: 'string',
  },
});
</script>

<template>
  <input
    :type="type"
    :placeholder="placeHolder"
    :value="value"
    @input="(e) => $emit('update', e.target.value)"
    :class="[
      'border-2',
      'p-2',
      'mt-1',
      'border-sol-grey-2',
      'focus:border-sol-yellow-1',
      'dark:focus:border-sol-blue-1',
      'rounded-md',
      'dark:bg-sol-black-2',
      'outline-none',
    ]"
  />
</template>

<style lang="css">
/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type='number'] {
  -moz-appearance: textfield;
}
</style>
