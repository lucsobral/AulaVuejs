<template>
  <div class="container my-5">
        <div class="row">
            <div class="col" id="conteudo-principal">
                <div class="card">
                    <div class="card-header">
                        Cadastro de Usuário
                    </div>
                    <div class="card-body">

                        <form id="meuForm" class="needs-validation" novalidate>
                            <div class="form-row">
                                <div class="col-md-6 mb-3">
                                    <label for="txtFirstName">Primeiro Nome</label>
                                    <input type="text" class="form-control" v-model="txtFirstName" required>
                                    <div class="valid-feedback">
                                        Looks good!
                                    </div>
                                </div>
                                <div class="col-md-6 mb-3">
                                    <label for="validationCustom02">Sobrenome</label>
                                    <input type="text" class="form-control" v-model="txtLastName" required>
                                    <div class="valid-feedback">
                                        Looks good!
                                    </div>
                                </div>
                            </div>
                            <input type="hidden" id="txtId">
                            <button class="btn btn-primary" id="btnEnviar" type="button" @click="InsertEmployee">Enviar Formulário</button>
                            <button class="btn btn-primary" type="button" disabled>
                                <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
                                Loading...
                            </button>
                        </form>

                        <div class="row mt-5">
                            <div class="col-8">
                                <table class="table">
                                    <thead>
                                        <th scope="col">Primeiro Nome</th>
                                        <th scope="col">Sobrenome</th>
                                        <th scope="col">Ações</th>
                                    </thead>
                                    <tbody id="gridPessoas">
                                        <tr v-for="employee in employees" :key="employee.Id">
                                            <td class="firstName">{{employee.FirstName}}</td>
                                            <td class="lastName">{{employee.LastName}}</td>
                                            <td>
                                                <button class="btn btn-primary" @click="deleteEmployee($event)"><i class="fa fa-edit"></i></button>
                                                <button class="btn btn-danger"><i class="fa fa-trash"></i></button>
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
    data(){
        return {
            txtFirstName: '',
            txtLastName: '',
            employees: [
                {
                    Id: 1,
                    FirstName: 'Lucas',
                    LastName: 'Sobral'
                },
                {
                    Id: 2,
                    FirstName: 'Charles',
                    LastName: 'Wagner'
                }
            ]
        }
    },
    methods:{
        InsertEmployee: function(){
            this.employees.push({
                Id: getRandomIntInclusive(1, 1000),
                FirstName: this.txtFirstName,
                LastName: this.txtLastName
            });
            this.txtFirstName = '';
            this.txtLastName = '';
        },
        deleteEmployee: function(){
            console.log(this);
        }
    }
}

function getRandomIntInclusive(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
</script>

<style>

</style>