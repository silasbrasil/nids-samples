<template lang="pug">
  #app.nids-layout-column.nids-layout-fill
    router-view
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class App extends Vue {}
</script>

<style lang="scss">
@import "~@niduu/nids-theme/nids-theme--layout.css";
@import "~@niduu/nids-theme/nids-theme--fonts.css";
@import "~@niduu/nids-icons/nids-icons.css";
@import "~@niduu/nids-placeload/nids-placeload.css";

html, body {
  height: 100%;
}

#app {
  @include nids-typography-primary();
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
