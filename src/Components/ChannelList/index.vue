<template lang="pug">
  .container
    .category
      div Canais de Texto
      .category-icon
        AddCategoryIcon(:size="21")
    ChannelButton(channelName="chat-livre" selected)
    ChannelButton(channelName="trabalho")
    ChannelButton(channelName="lolzinho")
    ChannelButton(channelName="valorant")
    ChannelButton(channelName="csgo")
</template>

<script>
import AddCategoryIcon from 'vue-material-design-icons/Plus'
import ChannelButton from './ChannelButton'
export default {
  components: {
    AddCategoryIcon,
    ChannelButton
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
  grid-area: CL; /* Diz que a grid-area que essa div filha irá ocupar é a de sigla CL (ChannelList) */

  background-color: var(--secondary);

  /**
   * .:: Alinhamento e Posicionamento ::.
   */
  display: flex;
  flex-direction: column;

  padding: 24px 10px 0 16px;
}

.category {
  color: var(--grey);

  /**
   * .:: Alinhamento ::.
   */
  display: flex;
  align-items: center;
  justify-content: space-between;

  /**
   * .:: Espaçamento ::.
   */
  margin-bottom: 6px;

  /**
   * .:: Estilizando texto ::.
   */
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;

  .category-icon {
    color: var(--symbol);
    cursor: pointer;
  }
}
</style>