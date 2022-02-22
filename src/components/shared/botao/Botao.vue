<template>
  <button class="botao" :class="classeBotao" @click="disparaEvento()">
    {{ rotulo }}
  </button>
</template>

<script>
export default {
  props: {
    tipo: {
      type: String,
      required: true
    },

    rotulo: {
      type: String,
      required: true
    },

    confirmacao: Boolean,
    estilo: String
  },
  methods: {
    disparaEvento() {
      if (this.confirmacao) {
        if (confirm("Você tem certeza?")) {
          this.$emit("botaoAcionado");
        }
      } else {
        this.$emit("botaoAcionado");
      }
    }
  },

  computed: {
    classeBotao() {
      if (!this.tipo || this.tipo == "padrao") return "botao-padrao";
      if (this.tipo == "perigo") return "botao-perigo";
    }
  }
};
</script>

<style scoped>
.botao {
  display: inline-block;
  padding: 10px;
  border-radius: 3px;
  margin: 10px;
  font-size: 1.2em;
}

.botao-perigo {
  background: firebrick;
  color: white;
}

.botao-padrao {
  background: darkcyan;
  color: white;
}
</style>
