<template>
    <div>
        <img src="../assets/img/ilustra_buscavazia.svg" alt="Fone desplugado">
        <div class="title">
            {{ message }}
        </div>
        <p v-if="statusCode === 404">
            <nuxt-link to="/">
              Que tal retornar para a página principal?
            </nuxt-link>
        </p>
    </div>
</template>

<script>
    export default {
        props: {
            error: {
                type: Object,
                default: null
            }
        },
        head() {
            return {
                title: this.message
            }
        },
        computed: {
            statusCode() {
                return (this.error && this.error.statusCode) || 500
            },
            message() {
                return this.error.message
            }

        }
    }
</script>

<style lang="scss" scoped>

</style>