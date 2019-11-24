<template functional>
  <svg
    viewBox="0 0 24 24"
    class="icon"
    :class="$options.methods.getStyleClasses(props)"
    v-bind="data.attrs"
    v-on="listeners"
    role="img"
  >
    <title>{{ props.title || props.name }}</title>
    <desc v-if="props.desc">{{ props.desc }}</desc>
    <path :d="$options.methods.getPath(props)" />
  </svg>
</template>

<script>
import icons from './icons.json';

export default {
  name: "AppIcon",
  props: {
    name: String,
    size: String,
    color: String,
    title: String,
    desc: String,
  },
  methods: {
    getPath(props) {
      return icons[props.name];
    },
    getStyleClasses(props) {
      return [props.size, props.color].map(val => val && `is-${val}`);
    },
  },
};
</script>

<style>
/* default */
.icon {
  width: 1.2em;
  height: 1.2em;
  fill: currentColor;
}

/* sizes */
.icon.is-large {
  width: 2em;
  height: 2em;
}
.icon.is-medium {
  width: 1.6em;
  height: 1.6em;
}
.icon.is-normal {
  width: 1.2em;
  height: 1.2em;
}
.icon.is-small {
  width: 1em;
  height: 1em;
}
.icon.is-tiny {
  width: 0.8em;
  height: 0.8em;
}

/* colors */
.icon.is-primary,
.icon.is-blue {
  fill: #2196F3
}
.icon.is-success,
.icon.is-green {
  fill: #4CAF50
}
.icon.is-danger,
.icon.is-red  {
  fill: #F44336
}
.icon.is-warning,
.icon.is-orange {
  fill: #FF9800
}
</style>