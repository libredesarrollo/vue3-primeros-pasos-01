<template>
  <div>
    <h1>Hola Mundo</h1>

    <!-- **EVENTOS -->
    <p v-on:click="molesto = negritas = !molesto">{{ valor }}</p>
    <!-- **EVENTOS FIN -->

    <!-- **CONDICIONES -->
    <!-- v-model -->
    <input v-if="setDefaultValue" type="number" v-model="valor" />

    <div v-else-if="valor == 5">Los dioses me dicen que valor es 5</div>
    <div v-else>Ya no hay campo jaja</div>
    <!-- **CONDICIONES FIN -->

    <!-- **CICLOS -->
    <div v-for="(c, index) in array" v-bind:key="c.id">
      <h3>{{ c.name }} {{ index }}</h3>
    </div>

    <hello-world v-for="c in [1, 2, 3, 4, 5]" v-bind:key="c.id" />
    <!-- **CICLOS FIN-->
    <br />

    <!-- **EVENTOS -->
    <!-- <button @click="myClick">Dame un click</button> -->
    <button @click="contador(1)">+1</button>
    <button @click="contador(-1)">-1</button>
    <br />
    <button @click="valor++">+1</button>
    <button @click="valor--">-1</button>
    <!-- **EVENTOS FIN -->

    <!-- **RAW HTML -->
    <p>
      {{ rawhtml }}
    </p>
    <p v-html="rawhtml"></p>
    <!-- **RAW HTML FIN-->

    <!-- **CLASES -->
    <!-- Objeto sintaxis -->
    <p class="italic" :class="{ rojo: molesto, negritas: negritas }">
      Texto con clases
    </p>
    <!--  Syntaxis array -->
    <p class="italic" :class="['green', rojo]">Texto con clases array</p>
    <!-- Condicionales -->
    <div :class="[molesto ? rojo : 'green', 'default']">
      Estado Animo (array con condicionales)
    </div>

    <div :class="[{ green: !molesto }, 'default']">
      Estado Animo (array con condicionales)
    </div>

    <!-- **CLASES FIN -->

    <!-- **ESTILOS -->
    <div :style="{ color: colorProperty }">Estilos</div>
    <!-- **ESTILOS FIN -->

    
  </div>
</template>

<style scoped>
h1 {
  color: red;
}
</style>

<script>
import HelloWorld from "./HelloWorld";

export default {
  name: "otro",
  data() {
    return {
      colorProperty: "#F0F",
      rojo: "rojo",
      molesto: false,
      negritas: false,
      valor: 0,
      rawhtml: "<span style='color:red'>Hola texto rojo</span>",
      array: [
        {
          id: "123",
          name: "andres",
        },
        {
          id: "1234",
          name: "juan",
        },
      ],
      setDefaultValue: true,
    };
  },
  //props:['title'],
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  methods: {
    myClick: function () {
      this.valor = "andres";

      alert("NO!!!");
    },
    contador(v) {
      this.valor += v;
    },
  },
  computed: {
    mutiplicarPorCinco() {
      console.log("dentro de computado");
      return this.valor * 5;
    },
  },
  components: {
    HelloWorld,
  },
  watch: {
    valor: function (newValue, oldValue) {
      this.setDefaultValue = false;
      console.log("newValue " + newValue + " oldValue " + oldValue);
    },
  },
};
</script>
<style>
.italic {
  font-style: italic;
}
.rojo {
  color: red;
}
.negritas {
  font-weight: bold;
}
.green {
  color: green;
}
</style>