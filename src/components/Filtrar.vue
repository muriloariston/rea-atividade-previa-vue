<template>
  <div id="app" class="container">
    <div class="card">
      <div class="card-header">
        <div class="form-row">
          <div class="form-group">
            <label for="inputTexto"
              >Texto (pressione [Enter] para filtrar os números)</label
            >
            <input
              autofocus
              @keyup.enter="filterText($event.target.value)"
              type="text"
              name="inputTexto"
              class="form-control"
              placeholder="Novo Texto"
            />
          </div>
        </div>
      </div>
      <div class="card-body">
        <h5 class="card-title">Números:</h5>
        <div>{{ numeros }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Filtrar",
  data() {
    return { numeros: "" };
  },
  methods: {
    filterText: function (text) {
      let numb = text.match(/\d/g);
      numb = numb.join("");
      this.numeros = numb;
    },
  },
};
</script>