<template>
    <div class="d-flex flex-column h-100">
        <nav class="py-2 bg-primary border-bottom">
            <div class="container d-flex flex-wrap">
                <div>
                    <router-link to="/"><button type="button" class="btn btn-outline-light me-2">Página Inicial</button>
                    </router-link> |
                    <router-link to="/login"><button type="button" class="btn btn-warning">Login</button>
                    </router-link> |
                    <router-link to="/cadastrar"><button type="button" class="btn btn-secondary me-2">Cadastre-se</button>
                    </router-link>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>