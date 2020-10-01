<template>
  <ul class="list-group">
    <li class="list-group-item active">Serviços Públicos</li>
    <li class="list-group-item" v-for="menu in menus" :key="menu.id">
      <RightMenuHref :link="menu.link" :description="menu.description"/>
    </li>
  </ul>
</template>

<script>
import RightMenuHref from "./RightMenuHref.vue";
export default {
  components: {
    RightMenuHref,
  },
  data() {
    return {
      menus: [
        {
          id: Math.floor(Math.random() * 1000),
          link: "https://globo.com",
          description: "Processos Eletrônicos",
        },
        {
          id: Math.floor(Math.random() * 1000),
          link: "https://uol.com",
          description: "Processos Físicos",
        },
      ],
    };
  },
};
</script>

<style>
</style>