<template lang="pug">
  .container
    .profile
      .avatar
      .userdata
        strong Guilherme Esdras
        span #1900
    .actions
</template>

<script>
import Mic from "vue-material-design-icons/Microphone";
import HeadPhones from "vue-material-design-icons/Headphones";
import Settings from "vue-material-design-icons/CogOutline";
export default {
  components: {
    Mic,
    HeadPhones,
    Settings
  }
};
</script>

<style lang="scss" scoped></style>
