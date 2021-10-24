<template lang="pug">
  .container
    .icon
      HashTagIcon(:size="24")
    h1.title chat-livre
    .separator
    .description Canal aberto para conversas
</template>

<script>
import HashTagIcon from "vue-material-design-icons/Pound";
export default {
  components: {
    HashTagIcon
  }
};
</script>

<style lang="scss" scoped>
.container {
  /**
   * Como a div "mãe" foi especificada como um tipo de caixa Grid (display grid), então, essa div filha ocupa uma grid-area
   * Nesse caso, deve-se específicar qual grid-area essa div filha irá ocupar, atribuindo a sigla ao atributo 'grid-area'
   * As grid-area's são definidas na div mãe no atributo "grid-template-areas"
   */
  grid-area: CI; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla CI (ChannelInfo) */

  background-color: var(--primary);
  box-shadow: rgba(0, 0, 0, 0.9) 0 1px 0 0;

  display: flex;
  align-items: center;
  padding: 0 17px; /* verical | horizontal */

  z-index: 2;

  .icon {
    color: var(--symbol);
  }

  .title {
    color: var(--white);
    font-size: 16px;
    font-weight: bold;
    margin-left: 9px; /* Distância da HashTag */
  }

  .description {
    color: var(--grey);
    font-size: 15px;
  }

  .separator {
    background-color: var(--white);
    width: 1px;
    height: 24px;
    opacity: 0.2;
    margin: 0 13px;
  }
}
</style>
