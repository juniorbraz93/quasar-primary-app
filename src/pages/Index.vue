<template>
  <q-page class="container flex column flex-center justify-around">
    <h4 class="title q-ma-sm text-center">
      <strong>{{ phrases[index] }}</strong>
    </h4>

    <q-img
      src="../assets/paisagem.jpeg"
      spinner-color="white"
      style="height: auto; max-width: 260px; border-radius: 10px"
    />

    <div class="flex justify-around full-width">
      <q-btn
        class="btn"
        outline
        rounded
        @click="randomPhrase"
        label="Gerar Frase"
      />

      <q-btn class="btn" rounded @click="randomPhrase" label="Gerar Frase" />
    </div>
  </q-page>
</template>

<script>
export default {
  name: "PharseOfDay",
  data() {
    return {
      phrases: [
        "Enfrente os problemas e leve a melhor!",
        "Respire fundo e fique atento às surpresas deliciosas que a vida preparou para você!",
        "Levanta, sacode a poeira, dá a volta por cima.",
        "Nem todos os dias são bons, mas há algo bom em cada dia.",
        "Não se exija demais",
        "Respeite sua mente e trate seu corpo com carinho.",
      ],
      index: 0,
    };
  },
  methods: {
    randomPhrase() {
      let index = parseInt(Math.random() * 6 + 0);
      this.index = index;
    },
  },
  beforeMount() {
    this.randomPhrase();
  },
};
</script>

<style lang="stylus" scoped>
.container{
  background-color: #f95179;
}

.title{
  color: #fff;
}

.btn{
  text-align: 'center';
  background-color: #262525;
  color: #fff;
  height: 60px;
}
</style>
