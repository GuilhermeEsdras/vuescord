<template lang="pug">
  .channel-list(:class="{ active: selected }")
    .channel-info
      HashTagIcon.hash-icon(:size="20")
      div {{channelName}}
    .channel-actions
      InviteIcon.icon-actions(:size="16")
      SettingsIcon.icon-actions(:size="16")
</template>

<script>
import HashTagIcon from 'vue-material-design-icons/Pound'
import InviteIcon from 'vue-material-design-icons/AccountPlus'
import SettingsIcon from 'vue-material-design-icons/CogOutline'
export default {
  components: {
    HashTagIcon,
    InviteIcon,
    SettingsIcon
  },
  props: {
    channelName: String,
    selected: Boolean
  }
}
</script>

<style lang="scss" scoped>
.channel-list {
  /**
   * .:: Alinhamento e Posicionamento ::.
   */
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  padding: 5px 3px;
  border-radius: 5px;
  background-color: transparent;

  /**
   * Todas as divs filhas de 'channel-list'
   */
  > div {
    display: flex;
    align-items: center;
  }

  .channel-info {
    div {
      color: var(--senary);
      margin-left: 5px;
    }

    .hash-icon {
      color: var(--symbol);
    }
  }

  .channel-actions {
    display: none;
    .icon-actions {
      color: var(--symbol);
      margin-left: 4px;
      transition: 0.2s;
      &:hover {
        color: var(--white);
      }
    }
  }

  &.active,
  &:hover {
    background-color: var(--quinary);

    .channel-info {
      div {
        color: var(--white);
      }
    }

    .channel-actions {
      display: flex;
    }
  }
}
</style>