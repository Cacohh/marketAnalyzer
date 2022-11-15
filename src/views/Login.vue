<template>
    <div lass="login">
        <div class="text-center">
            <main class="form-signin w-100 m-auto">
                <form>
                    <img class="mb-4" src="https://upload.wikimedia.org/wikipedia/commons/8/86/Senac_logo.svg" alt=""
                        width="72" height="57">
                    <h1 class="h3 mb-3 fw-normal">Login</h1>

                    <div class="form-floating">
                        <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">
                        <label for="floatingInput">Endereço de E-mail</label>
                    </div>
                    <div class="form-floating">
                        <input type="password" class="form-control" id="floatingPassword" placeholder="Password">
                        <label for="floatingPassword">Senha</label>
                    </div>
                    <div class="checkbox mb-3">
                        <label>
                            <input type="checkbox" value="remember-me"> Lembre-se de mim
                        </label>
                    </div>

                    <input class="w-100 btn btn-lg btn-primary mb-2" type="button" value="Entrar" onclick="entrada()">

                    <a href="/cadastro.html"><input class="w-100 btn btn-sm btn-warning mb-2" type="button"
                            value="Criar Novo Cadastro"></a>
                    <a href="/senha_recuperar.html"><input class="w-100 btn btn-sm btn-secondary mb-2" type="button"
                            value="Recuperar Senha"></a>

                    <p class="mt-5 mb-3 text-muted">&copy; 2017–2022</p>
                </form>
            </main>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Login'
}
</script>