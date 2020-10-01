<template>
  <div id="app">
    <TopMenu />
    
    <div class="container my-3">
        <div class="row">
            <div class="col-lg-9 col-xs-12" id="conteudo-principal">
                <div class="row">
                    <div class="col">
                        <HorizontalNews date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..." />
                    </div>
                </div>
                <hr />
                <div class="row mb-3">
                    <div class="col">
                        <HorizontalNews date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..." />
                    </div>
                </div>

                <div class="row">
                    <div class="col-sm-12 col-lg-4">
                        <News date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..."  />
                    </div>
                    <div class="col-sm-12 col-lg-4">
                        <News date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..." />
                    </div>
                    <div class="col-sm-12 col-lg-4">
                        <News date="2021-07-06 15:50:53" title="Hotsite do TRFMED registra todas as ações da Autogestão em Saúde" resume="O Programa de Autogestão em Saúde da Justiça Federal da 5ª Região(TRFMED) tem..." />
                    </div>
                </div>
            </div>
            <RightContent />
            
        </div>
    </div>


  </div>
</template>

<script>
import TopMenu from './components/TopMenu.vue'
import HorizontalNews from './components/HorizontalNews.vue'
import News from './components/News.vue'
import RightContent from './components/RightContent.vue'

export default {
  name: 'App',
  components: {
    TopMenu,
    HorizontalNews,
    News,
    RightContent
  }
}
</script>

<style>

</style>
