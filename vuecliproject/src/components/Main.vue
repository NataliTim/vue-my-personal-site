<template>
    <div id="app">
        <div class="container">
            <div class="lang_wrapper">
                <LocaleSwitcher/>
            </div>
            <p>{{ $t('main.title') }}</p>
            <p>{{ $t('main.slogan') }}</p>
            <div class="alert alert-success alert-dismissible fade show" role="alert">
                With Bootstrap!
                <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                </button>
            </div>
        </div>
    </div>
</template>

<script>
    import LocaleSwitcher from './LocaleSwitcher.vue'

    export default {
        data() {
            return {
            }
        },
        components: {
            LocaleSwitcher
        },
        methods: {
            countDownChanged(dismissCountDown) {
                this.dismissCountDown = dismissCountDown
            },
            showAlert() {
                this.dismissCountDown = this.dismissSecs
            }
        }
    }
</script>

<style>

</style>