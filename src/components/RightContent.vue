<template>
  <div class="col-lg-3 col-xs-12" id="conteudo-lateral">
    <RightMenu />
    <br/>
    <RightMenu />
    <br />
    <News date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..." />
  </div>
</template>

<script>
import RightMenu from './RightMenu.vue'
import News from './News.vue'

export default {
    components: {
        RightMenu,
        News
    }
};
</script>

<style>
</style>