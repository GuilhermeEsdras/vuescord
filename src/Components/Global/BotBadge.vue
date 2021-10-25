<template lang="pug">
  .bot-badge
    CheckIcon.check-icon(:size="9" v-if="isVerified")
    span Bot
</template>

<script>
import CheckIcon from 'vue-material-design-icons/CheckBold'
export default {
  components: {
    CheckIcon
  },
  props: {
    isVerified: Boolean
  }
}
</script>

<style lang="scss" scoped>
.bot-badge {
  background-color: var(--discord);
  color: var(--white);
  
  margin-left: 9px; /* Distância do badge pro nome do usuário */
  padding: 3px 4px;
  border-radius: 4px;

  text-transform: uppercase;
  font-size: 10px;
  font-weight: bold;
}

.check-icon {
  padding: 1px;
}
</style>