<template>
  <div class="container">
    <ServerButton isHome />
    <div class="separator"></div>
    <ServerButton :mentions="3" /> <!-- VueJS: Se a propriedade for número, coloca ":" no início -->
    <ServerButton hasNotification />
    <ServerButton :mentions="32" hasNotification />
    <ServerButton v-for="servers in 18" :key="servers.id" />
    <ServerButton />
  </div>
</template>

<script>
import ServerButton from './ServerButton'

export default {
  components: {
    ServerButton
  }
}
</script>


<style scoped lang="scss">
.container {
  background-color: var(--tertiary); /* Usa a variável global da cor terciária */

  padding: 11px 0; /* Top & Bottom = 11px | Right & Left = 0px */

  display: flex; /* O tipo de caixa dessa div será FlexBox */
  flex-direction: column; /* Alinhar os botões um em baixo do outro em estilo coluna */
  align-items: center; /* Alinha os items (nesse caso, os botões) ao centro da coluna */
  
  max-height: 100vh; /* Altura máxima = 100% da altura disponível */

  /**
   * Como a div "mãe" foi especificada como um tipo de caixa Grid (display grid), então, essa div filha ocupa uma grid-area
   * Nesse caso, deve-se específicar qual grid-area essa div filha irá ocupar, atribuindo a sigla ao atributo 'grid-area'
   * As grid-area's são definidas na div mãe no atributo "grid-template-areas"
   */
  grid-area: SL; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla SL (ServerList) */

  overflow-y: scroll; /* Cria uma barra de rolagem caso o número de botões ultrapasse a view disponível */
  &::-webkit-scrollbar {
    display: none; /* Deixa a barra transparente */
  }
}

.separator {
  border-bottom: solid 2px var(--quaternary);
  width: 32px;
  margin-bottom: 8px;
}
</style>