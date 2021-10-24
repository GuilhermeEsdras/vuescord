<template lang="pug">
  .container
    .messages
      Message(v-for="msg in 50" :key="msg.id")
    .input-wrapper
      input(type="text" placeholder="Conversar em #chat-livre")
      .icon
        At(:size="24")
</template>

<script>
import Message from "./Message";
import At from "vue-material-design-icons/At";
export default {
  components: {
    Message,
    At
  }
};
</script>

<style lang="scss" scoped>
.container {
  grid-area: CD;

  background-color: var(--primary);

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  flex: 1; /* Ocupa todo o espaço disponível */

  .messages {
    // Alinhando mensagens uma embaixo da outra:
    display: flex;
    flex-direction: column;

    /**
     * O cálculo à seguir define a altura da caixa de mensagens usando os seguintes valores:
     * 100vh = 100% do espaço visível da tela
     * 46px = Altura do ChannelName
     * 68px = Altura do input-wrapper
     */
    height: calc(100vh - 46px - 68px);
    max-height: calc(100vh - 46px - 68px);

    overflow-y: scroll; /* Se houverem mais elementos do que o max-height cabe, coloca a scrollbar */

    /**
     * .:: Estilizando a Scrollbar (barra de rolagem) ::.
     */
    &::-webkit-scrollbar {
      width: 8px;
    }
    &::-webkit-scrollbar-thumb {
      /* Área interna */
      background-color: var(--tertiary);
      border-radius: 4px;
    }
    &::-webkit-scrollbar-track {
      /* Área externa */
      background-color: var(--secondary);
      border-radius: 4px;
    }
  }

  .input-wrapper {
    width: 100%;
    height: 68px;
    padding: 0 16px;

    input {
      color: var(--white);
      background-color: var(--chat-input);

      position: relative;

      width: 100%;
      height: 44px;
      padding: 0 10px 0 57px;

      border-radius: 5px;

      &::placeholder {
        color: var(--grey);
      }
    }

    .icon {
      color: var(--grey);

      position: relative;

      top: -50%;
      left: 14px;
      width: 24px;

      transition: 0.2s;
    }
  }
}
</style>
