<template>
    <div class="text-center">
        <main class="form-signin w-100 m-auto">
            <form @submit.prevent="logar()">
                <img class="mb-4" src="store-png.png" alt="" width="72" height="70">
                <h1 class="h3 mb-3 fw-normal">Login</h1>

                <div v-if="status" class="alert alert-danger" role="alert">
                    E-mail ou senha incorretos! Tente novamente por favor.
                </div>

                <div class="form-floating">
                    <input type="email" class="form-control" id="floatingInput" v-model="email"
                        placeholder="name@example.com">
                    <label for="floatingInput">Endereço de E-mail</label>
                </div>
                <div class="form-floating">
                    <input type="password" class="form-control" id="floatingPassword" v-model="senha"
                        placeholder="Password">
                    <label for="floatingPassword">Senha</label>
                </div>
                <div class="checkbox mb-3">
                    <label>
                        <input type="checkbox" value="remember-me"> Lembre-se de mim
                    </label>
                </div>

                <input class="w-100 btn btn-lg btn-primary mb-2" type="submit" value="Entrar">

                <a href="/senha_recuperar.html"><input class="w-100 btn btn-sm btn-warning  mb-2" type="button"
                        value="Recuperar Senha"></a>

                <p class="mt-5 mb-3 text-muted">&copy; 2017–2022</p>
            </form>
        </main>
    </div>
</template>

<script>
export default {
    name: 'Login',
    data() {
        return {
            email: "",
            senha: "",
            status: false
        }
    },
    methods: {
        async logar() {
            const email = this.email;
            const senha = this.senha;
            const req = await fetch("http://144.217.133.81:3000/usuarios");
            const data = await req.json();
            for (const usuario of data) {
                if (email == usuario.email && senha == usuario.senha) {
                    this.$router.push({ path: '/home' })
                }
            }

            this.status = true
        }
    }
}
</script>
   
<style scoped>
html,
body {
    height: 100%;
}

body {
    display: flex;
    align-items: center;
    padding-top: 40px;
    padding-bottom: 40px;
    background-color: #f5f5f5;
}

.form-signin {
    max-width: 330px;
    padding: 15px;
}

.form-signin .form-floating:focus-within {
    z-index: 2;
}

.form-signin input[type="email"] {
    margin-bottom: -1px;
    border-bottom-right-radius: 0;
    border-bottom-left-radius: 0;
}

.form-signin input[type="password"] {
    margin-bottom: 10px;
    border-top-left-radius: 0;
    border-top-right-radius: 0;
}

.bd-placeholder-img {
    font-size: 1.125rem;
    text-anchor: middle;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
}

@media (min-width: 768px) {
    .bd-placeholder-img-lg {
        font-size: 3.5rem;
    }
}

.b-example-divider {
    height: 3rem;
    background-color: rgba(0, 0, 0, .1);
    border: solid rgba(0, 0, 0, .15);
    border-width: 1px 0;
    box-shadow: inset 0 .5em 1.5em rgba(0, 0, 0, .1), inset 0 .125em .5em rgba(0, 0, 0, .15);
}

.b-example-vr {
    flex-shrink: 0;
    width: 1.5rem;
    height: 100vh;
}

.bi {
    vertical-align: -.125em;
    fill: currentColor;
}

.nav-scroller {
    position: relative;
    z-index: 2;
    height: 2.75rem;
    overflow-y: hidden;
}

.nav-scroller .nav {
    display: flex;
    flex-wrap: nowrap;
    padding-bottom: 1rem;
    margin-top: -1px;
    overflow-x: auto;
    text-align: center;
    white-space: nowrap;
    -webkit-overflow-scrolling: touch;
}
</style>