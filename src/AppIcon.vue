<template>
  <svg class="icon" style="width:24px;height:24px" viewBox="0 0 24 24">
    <path :d="path" />
  </svg>
</template>

<script>
export default {
  name: 'AppIcon',
  props: {
    path: String,
  },
};
</script>