<template>
  <div class="serverbutton">

  </div>
</template>

<style scoped lang="scss">
.serverbutton {
  background-color: var(--primary); /* Usa a variável global da cor primária */

  width: 48px;
  height: 48px;
  border-radius: 50%; /* Funciona assim quando o elemento é quadrado */
  cursor: pointer;

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

  transition: 0.2s;

  &.active,
  &:hover {
    border-radius: 16px;
    background-color: var(--discord);
  }
}
</style>
