<template lang="pug">
  .user-row
    .avatar(:class="{ 'bot-avatar': isBot }")
    strong {{ nickname }}
    BotBadge(v-if="isBot" isVerified={isBotVerified})
</template>

<script>
import BotBadge from '../Global/BotBadge'
export default {
  components: {
    BotBadge
  },
  props: {
    nickname: String,
    isBot: Boolean,
    isBotVerified: Boolean
  }
};
</script>

<style lang="scss" scoped>
.user-row {
  margin-top: 5px;
  padding: 5px;

  display: flex;
  align-items: center;

  cursor: pointer;

  border-radius: 5px;
  background: transparent;
  transition: 0.2s;

  &:hover {
    background: rgba(0, 0, 0, 0.1);
  }

  .avatar {
    background: var(--primary);
    width: 32px;
    height: 32px;
    border-radius: 50%;
    flex-shrink: 0; /* Evitar distorção quando redimensionar a página */
  }

  .bot-avatar {
    background-color: var(--mention-detail);
  }

  strong {
    font-size: 14px;
    margin-left: 12px;
    font-weight: 400;
    color: var(--white);
    opacity: 0.7;

    /**
     * Tratando overflow no texto
     */
    white-space: nowrap; /* Para não quebrar de linha */
    text-overflow: ellipsis; /* O que exibir caso o texto não caiba no conteiner */
    overflow: hidden;
  }
}
</style>
