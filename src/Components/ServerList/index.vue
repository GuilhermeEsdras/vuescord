<template>
  <div class="container">
    <ServerButton />
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column; /* Alinhar os botões dos servidores um em baixo do outro em coluna */
  align-items: center; /* Alinha os botões ao centro */
  background-color: var(--tertiary);
  padding: 11px 0;
}
</style>