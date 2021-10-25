<template lang="pug">
  .container
    .role Disponível - 1
    UserRow(nickname="Esdras Guilherme")
    .role Offline - 18
    UserRow(nickname="Esdras Guilhermes" isBot isBotVerified)
    UserRow(nickname="Esdras 2" isBot)
    UserRow(nickname="Guilherme Esdras" v-for="users in 24" :key="users.id")
</template>

<script>
import UserRow from "./UserRow";
export default {
  components: {
    UserRow
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
  grid-area: UL; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla UL (UserList) */

  /**
   * .:: Cor e Estilo ::.
   */
  background-color: var(--secondary);

  /**
   * .:: Alinhamento ::.
   */
  display: flex;
  flex-direction: column;

  /**
   * .:: Espaçamento ::.
   */
  padding: 3px 6px 10px 16px;

  max-height: calc(100vh - 46px);

  /**
   * Tratando Overflow
   */
  overflow-y: scroll; /* Cria uma barra de rolagem caso o número de mensagens ultrapasse a view disponível */

  /**
    * .:: Estilizando a Scrollbar (barra de rolagem) ::.
    */
  &::-webkit-scrollbar {
    width: 4px;
  }
  &::-webkit-scrollbar-thumb {
    background-color: var(--tertiary);
    border-radius: 4px;
  }
  &::-webkit-scrollbar-track {
    background-color: var(--secondary);
  }

  // Título dos cargos:
  .role {
    color: var(--grey);

    margin-top: 20px;

    font-size: 12px;
    font-weight: 500;
    text-transform: uppercase;
  }
}
</style>
