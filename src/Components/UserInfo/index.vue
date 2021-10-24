<template lang="pug">
  .container
    .profile
      .avatar
      .userdata
        strong Guilherme Esdras
        span #1900
    .actions
      Mic(:size="20")
      HeadPhones(:size="20")
      Settings(:size="20")
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

<style lang="scss" scoped>
.container {
  /**
   * Como a div "mãe" foi especificada como um tipo de caixa Grid (display grid), então, essa div filha ocupa uma grid-area
   * Nesse caso, deve-se específicar qual grid-area essa div filha deverá ser posicionada, atribuindo a sigla ao atributo 'grid-area'
   * As grid-area's são definidas na div mãe no atributo "grid-template-areas"
   */
  grid-area: UI; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla UI (UserInfo) */

  /**
   * .:: Cor e estilo ::.
   */
  background-color: var(--quaternary);
  box-shadow: rgba(0, 0, 0, 0.2) 0 1px 0 0;

  /**
   * .:: Alinhamento ::.
   */
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  /**
   * .:: Posicionamento ::.
   */
  padding: 10px;

  .profile {
    display: flex;
    align-items: center;

    .avatar {
      background-color: var(--grey);
      width: 32px;
      height: 32px;
      border-radius: 50%;
    }

    .userdata {
      /**
       * Alinhando "nome em cima, tag em baixo"
       */
      display: flex;
      flex-direction: column;

      margin-left: 8px; /* Distância do nome pro avatar */
      font-size: 13px;

      strong {
        // Estilos do Nome
        display: block;
        color: var(--white);
      }

      span {
        // Estilos da Tag
        color: var(--grey);
      }
    }
  }

  .actions {
    color: var(--grey);

    span {
      cursor: pointer;

      transition: .2s;
      &:hover {
        color: var(--white);
      }
    }
  }
}
</style>
