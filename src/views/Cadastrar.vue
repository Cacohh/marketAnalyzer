<template>
    <div class="d-flex flex-column h-100">
        <div class="p-5 bg-light rounded-3">
            <form class="row g-3" @submit.prevent="cadastrar()">
                <div class="col-md-6">
                    <label for="inputEmail4" class="form-label">Nome</label>
                    <input type="text" class="form-control" id="inputEmail3" v-model="nome">
                </div>
                <div class="col-md-6">
                    <label for="inputEmail4" class="form-label">Sobrenome</label>
                    <input type="text" class="form-control" id="inputEmail4" v-model="sobrenome">
                </div>
                <div class="col-md-6">
                    <label for="inputEmail4" class="form-label">Email</label>
                    <input type="email" class="form-control" id="inputEmail5" v-model="email">
                </div>
                <div class="col-md-6">
                    <label for="inputPassword4" class="form-label">Senha</label>
                    <input type="password" class="form-control" id="inputPassword6" v-model="senha">
                </div>

                <div class="col-12">
                    <div class="form-check">
                        <input class="form-check-input" type="checkbox" id="gridCheck">
                        <label class="form-check-label" for="gridCheck">
                            Quero receber notificações
                        </label>
                    </div>
                </div>
                <div class="col-12">
                    <button type="submit" class="btn btn-primary" id="cadastrar">Cadastrar</button>
                </div>
            </form>

        </div>
    </div>
</template>

<script>
export default {
    name: 'Cadastrar',
    data() {
        return {
            email: "",
            nome: "",
            sobrenome: "",
            senha: ""
        }
    },
    methods: {
        async cadastrar() {

            const data = {
                email: this.email,
                nome: this.nome,
                sobrenome : this.sobrenome,
                senha: this.senha
            }

            const dataJson = JSON.stringify(data);

            const req = await fetch("http://localhost:3000/usuarios", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });
        }
    }
}
</script>