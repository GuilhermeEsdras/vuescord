<template lang="pug">
  .serverbutton(:class="{'serverbutton-isHome': isHome, 'serverbutton-hasNotification': hasNotification}")
    img(src='../../assets/discord.svg' v-if='isHome')
    .mentions(v-if='mentions') {{mentions}}
</template>

<script>
export default {
  props: {
    selected: Boolean,
    isHome: Boolean,
    hasNotification: Boolean,
    mentions: Number
  }
}
</script>

<style scoped lang="scss">
.serverbutton {
  background-color: var(--primary); /* Usa a variável global da cor primária */

  /**
   * .:: Cria a "bolinha" ::.
   */
  width: 48px;
  height: 48px;
  border-radius: 50%; /* Funciona assim quando o elemento é quadrado */
  cursor: pointer;

  /**
   * .:: Alinha ao centro e um embaixo do outro ::.
   */
  display: flex; /* O tipo de caixa desse componente será FlexBox */
  flex-shrink: 0; /* 0 para não mudar a proporção de largura ou altura se o tamanho da tela for reduzido */
  align-items: center;
  justify-content: center;

  margin-bottom: 8px; /* Separação de 8px entre um botão e outro */

  /**
   * Posição Relativa: O elemento fica em seu lugar em relação ao fluxo do documento, mas pode ser deslocado usando top e left
   * Mesmo quando deslocado, o seu lugar no espaço preenchido é preservado.
   */
  position: relative;

  img {
    width: 24px;
    height: 24px;
    color: #fff;
  }

  transition: 0.2s;

  &.active,
  &:hover {
    border-radius: 16px;
    background-color: var(--discord);
  }
}

.serverbutton-hasNotification {
  &::before {
    content: ""; /* Obrigatório para o ::before */

    background-color: var(--white);
    width: 9px;
    height: 9px;

    position: absolute; /* Abosolutamente Relativo ao botão */
    left: -17px; /* Joga o elemento 17px à esquerda pra fora do componente pai */
    top: calc(50% - 4.5px);

    border-radius: 50%;
    display: block;
  }
}

.serverbutton-isHome {
  background-color: var(--purple);

  &.active,
  &:hover {
    border-radius: 16px;
    background-color: var(--purple);
  }
}

.mentions {
  background-color: var(--notification);

  /**
   * .:: Posicionando no canto inferior direito ::.
   */
  position: absolute; /* Abosolutamente Relativo ao botão (fica ao centro sobrepondo a img) */
  bottom: -4px; /* 4px pra fora a baixo do botão */
  right: -4px; /* 4px pra fora a direita do botão */

  /**
   * .:: Estilizando texto ::.
   */
  font-size: 13px;
  color: var(--white);
  font-weight: bold;
  text-align: center;
  
  /**
   * .:: Tratando das bordas, arredondando e colocando espaçamento correto ::.
   */
  padding: 0 4px; /* 4px nas laterais */
  border-radius: 12px;
  border: solid 4px var(--quaternary);
  height: 24px;
}
</style>
