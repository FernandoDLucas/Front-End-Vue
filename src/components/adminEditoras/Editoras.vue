<template>
  <div class="col-lg-9 col-md-9 col-sm-12 col-xs-12">
    <div class="title">
      <h1>Editoras Cadastradas</h1>
    </div>
    <table class="table table-striped">
      <thead>
        <tr>
          <th>Nome</th>
          <th>Cidade</th>
          <th>Ano de Fundação</th>
          <th></th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="editora in editoras" :key="editora.editoraID">
          <td>{{editora.nome}}</td>
          <td>{{editora.cidade}}</td>
          <td>{{editora.anoFundacao}}</td>
          <td>
            <router-link :to="'/adminLivros/editarEditora/'+editora.editoraID">
              <i class="fa fa-pencil-square-o"></i>
            </router-link>
          </td>
          <td>
            <a @click="removerEditora(editora.editoraID)">
              <i class="fa fa-trash"></i>
            </a>
          </td>
        </tr>
      </tbody>
      
    </table>
  </div>
</template>
<script>
export default {
  computed: {
    editoras() {
      return this.$store.getters.todasEditoras;
    }
  },
  created() {
    this.$store.dispatch("todasEditoras");
  },
  methods: {
    removerEditora(id) {
      this.$store.dispatch("removerEditora", id);
    }
  }
};
</script>

