<template lang="pug">
  .channel-message(:class="{ 'has-mention': hasMention }")
    .avatar(:class="{ 'bot-avatar': isBot }")
    .message
      .user
        strong {{ author }}
        span.bot-badge(v-if="isBot") Bot
        span.date {{ date }}
      .body
        slot
</template>

<script>
export default {
  props: {
    author: String,
    date: String,
    hasMention: Boolean,
    isBot: Boolean
  }
};
</script>

<style lang="scss" scoped>
.channel-message {
  background-color: transparent;

  padding: 8px 16px;
  margin-top: 13px;
  margin-right: 4px;

  display: flex;
  align-items: center;

  // Caso seja uma mensagem com menção:
  &.has-mention {
    background-color: var(--mention-message);
    border-left: solid 2px var(--mention-detail);
  }

  .avatar {
    background-color: var(--secondary);

    width: 40px;
    height: 40px;
    border-radius: 50%;

    flex-shrink: 0; /* Para não distorcer quando redimensionar a janela */

    // Caso seja uma mensagem de um bot:
    &.bot-avatar {
      background-color: var(--mention-detail);
    }
  }

  .message {
    margin-left: 17px; /* Separando do avatar */
    height: 40px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    .user {

      position: relative;
      top: -4px;

      // Nome do Usuário
      strong {
        color: var(--white);
        font-size: 16px;
      }
  
      .bot-badge {
        background-color: var(--discord);
        color: var(--white);
  
        position: relative;
        top: -4px;
        
        margin-left: 9px; /* Distância do badge pro nome do usuário */
        padding: 3px 5px;
        border-radius: 4px;
  
        text-transform: uppercase;
        font-size: 10px;
        font-weight: bold;
      }
  
      .date {
        margin-left: 6px; /* Distância da data pro nome do usuário ou bot-badge */
        color: var(--grey);
        font-size: 13px;
      }

    }


    .body {
      color: var(--white);
      text-align: left;
      font-size: 16px;

      // Caso seja uma menção:
      .mention {
        background-color: var(--link);
        padding: 2px 2px;
        border-radius: 3px;
        cursor: pointer;

        &:hover {
          background-color: var(--link-hover);
        }
      }
    }
  }

  &:hover {
    background-color: var(--quaternary);
  }
}
</style>
