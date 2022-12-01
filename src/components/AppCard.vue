<script>
import AppMain from "./AppMain.vue";
export default {
  name: "AppCard",
  props: {
    info: Object,
  },
};
</script>

<template>
  <h4>
    <li>
      <div>
        <h4>
          Titolo: <small>{{ risposta.data.title }}</small>
        </h4>
      </div>
    </li>
  </h4>
</template>

<style></style>
