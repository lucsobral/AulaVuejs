<template>
  <div class="container my-5">
    <div class="row">
      <div class="col" id="conteudo-principal">
        <div class="card">
          <div class="card-header">Cadastro de Usuário</div>
          <div class="card-body">
            <form id="meuForm" class="needs-validation" novalidate>
              <div class="form-row">
                <div class="col-md-6 mb-3">
                  <label for="txtFirstName">Primeiro Nome</label>
                  <input type="text" class="form-control" placeholder="Primeiro nome" v-model="txtFirstName" required />
                  <div class="valid-feedback">Looks good!</div>
                </div>
                <div class="col-md-6 mb-3">
                  <label for="validationCustom02">Sobrenome</label>
                  <input type="text" class="form-control" v-model="txtLastName" required />
                  <div class="valid-feedback">Looks good!</div>
                </div>
              </div>
              <input type="hidden" :value="txtId" />
              <button class="btn btn-primary" @click="InsertEmplyee" type="button">Enviar Formulário</button>
            </form>

            <div class="row mt-5">
              <div class="col-8">
                <table class="table table-striped table-dark">
                  <thead>
                    <th scope="col">Primeiro Nome</th>
                    <th scope="col">Sobrenome</th>
                    <th scope="col">Ações</th>
                  </thead>
                  <tbody>
                    <tr v-for="employee in Employees" :key="employee.Id">
                      <td>{{employee.FirstName}}</td>
                      <td>{{employee.LastName}}</td>
                      <td>
                        <button class="btn btn-primary btnEdit" @click="EditEmployee(employee.Id)">
                          Editar
                          <i class="fa fa-edit"></i>
                        </button>
                        <button class="btn btn-danger btnRemove" @click="RemoveEmployee(employee.Id)">
                          Remover
                          <i class="fa fa-trash"></i>
                        </button>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      txtFirstName: "",
      txtLastName: "",
      txtId: "",
      Employees: [],
    };
  },
  methods: {
    InsertEmplyee: function () {
      //Verifico se o id está preenchido, se tiver é uma edição
      if (this.txtId === "") {
        //Adiciono o objeto na minha coleção Employees
        this.Employees.unshift({
          Id: Math.floor(Math.random() * 1000),
          FirstName: this.txtFirstName,
          LastName: this.txtLastName,
        });
      } else {
        //Edito meu objeto
        var employee = this.Employees.find((x) => x.Id == this.txtId);
        employee.FirstName = this.txtFirstName;
        employee.LastName = this.txtLastName;
      }

      this.txtFirstName = "";
      this.txtLastName = "";
      this.txtId = "";
    },
    //Carrego os dados do funcionario selecionado para os campos do formulário
    EditEmployee: function (id) {
      var employee = this.Employees.find((x) => x.Id == id);
      this.txtFirstName = employee.FirstName;
      this.txtLastName = employee.LastName;
      this.txtId = employee.Id;
    },
    RemoveEmployee: function(id){
      var pos = this.Employees.findIndex((i) => i.Id == id);
      this.Employees.splice(pos, 1);
    }
  },
};
</script>

<style>
.table-dark.table-striped tbody tr:nth-of-type(odd) {
    background-color: rebeccapurple;
}
</style>