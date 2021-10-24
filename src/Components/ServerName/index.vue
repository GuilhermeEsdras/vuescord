<template lang="pug">
  .container
    .title Servidor do Esdras
    .icon
      ExpandIcon(:size="28")
</template>

<script>
import ExpandIcon from 'vue-material-design-icons/ChevronDown'
export default {
  components: {
    ExpandIcon
  }
}
</script>

<style lang="scss" scoped>
.container {
  /**
   * Como a div "mãe" foi especificada como um tipo de caixa Grid (display grid), então, essa div filha ocupa uma grid-area
   * Nesse caso, deve-se específicar qual grid-area essa div filha irá ocupar, atribuindo a sigla ao atributo 'grid-area'
   * As grid-area's são definidas na div mãe no atributo "grid-template-areas"
   */
  grid-area: SN; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla SN (ServerName) */

  background-color: var(--secondary);

  /**
   * .:: Alinhamento e Posicionamento ::.
   */
  display: flex;
  align-items: center;
  justify-content: space-between; /* "cada um numa ponta" */

  /**
   * .:: Posicionamento ::.
   */
  padding: 0 11px 0 16px; /* 0 em cima | 11 na direita | 0 em baixo | 16 na esquerda */

  box-shadow: rgba(0,0,0,.9) 0 1px 0 0; /* cor + deslocamentos */
  z-index: 2; /* Ficar acima dos outros componentes pra sombra dele se sobressair */
}

.title {
  color: var(--white);
  font-size: 16px;
  font-weight: bold;
}
</style>