<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div>Test</div>
  <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded" />
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";
export default {
  methods: {
    onDecode(data) {
      alert(data);
      const sku = data.split("|")[0];
      if (sku) {
        alert(sku);
      }
    },
    onLoaded() {
      console.log("load");
    },
  },
  name: "App",
  components: {
    StreamBarcodeReader,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
