<template lang='jade'>
  footer.p2
    .contain
      p
        em @copyrights.
</template>

<script>
const gekkoPackage = require('../../../../../package.json');
const uiPackage = require('../../../package.json');

export default {
  data: () => {
    return {
      version: {
        gekko: gekkoPackage.version,
        ui: uiPackage.version
      }
    }
  }
}
</script>
<style>
footer{
  background-color: #000 !important;
}
</style>
