<template>
  <div>
    <h1>{{ titulo }}</h1>
    <ul>
      <li v-for="foto of fotos">
        <img :src="foto.url" :alt="foto.titulo" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titulo: "Alurapic",
      fotos: [
        {
          url:
            "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/social/monkey_king.jpg",
          titulo: "dota2-mk"
        },
        {
          url:
            "https://lucrorpg.com/wp-content/uploads/2021/08/king-louis-II-the-younger-of-italy.webp",
          titulo: "ck3"
        }
      ]
    };
  }
};
</script>

<style></style>
