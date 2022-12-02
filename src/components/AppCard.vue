<script>
export default {
  name: "AppCard",
  props: {
    info: Object,
  },
};
</script>

<template>
  <h4>{{ info.title }}</h4>
</template>

<style></style>
