<template lang="pug">
  #grid
    ServerList
    ServerName
    ChannelList
    UserInfo
    ChannelInfo
</template>

<script>
import ServerList from "./ServerList";
import ServerName from "./ServerName";
import ChannelList from "./ChannelList";
import UserInfo from "./UserInfo";
import ChannelInfo from "./ChannelInfo";

export default {
  components: {
    ServerList,
    ServerName,
    ChannelList,
    UserInfo,
    ChannelInfo
  }
};
</script>

<style scoped>
#grid {
  display: grid; /* O tipo de caixa dessa div será Grid, por isso, seus filhos terão grid-area's */
  height: 100vh; /* Ocupa 100% da altura disponível */
  grid-template-columns: 71px 240px auto 240px; /* O Grid terá 4 colunas, cada coluna com esses respectivos tamanhos */
  grid-template-rows: 46px auto 52px; /* O Grid terá 3 linhas, cada linha com esses respectivos tamanhos */

  /**
   * .:: Aqui fica a organização dos espaços do Grid ::.
   * 
   * São 3 Linhas x 4 Colunas = 12 Siglas
   * Cada Sigla representa um componente
   * 
   * Significado de cada sigla:
   * SL = Server List (ocupará toda a primeira coluna e todas as 3 linhas dessa coluna)
   * SN = Server Name (ocupará apenas a primeira linha da segunda coluna)
   * CI = Channel Info (ocupará as duas últimas colunas da primeira linha)
   * CL = Channel List (ocupará a linha do meio da segunda coluna)
   * CD = Channel Date (ocupará as duas últimas linhas da terceira coluna)
   * UL = User List (ocupará as duas últimas linhas da última coluna)
   * UI = User Info (ocupará a última linha da segunda coluna)
   */
  grid-template-areas:
    "SL SN CI CI"
    "SL CL CD UL"
    "SL UI CD UL";
}
</style>
