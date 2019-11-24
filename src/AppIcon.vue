<template>
  <svg
    class="icon"
    style="width:24px;height:24px"
    viewBox="0 0 24 24"
  >
    <path :d="path" />
  </svg>
</template>

<script>
import icons from './icons.json';

export default {
  name: "AppIcon",
  props: {
    name: String,
  },
  computed: {
    path() {
      return icons[this.name];
    },
  },
};
</script>