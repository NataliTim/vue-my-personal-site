<template>
    <div id="app">
        <div class="wrapper">
        <div class="lang_wrapper">
            <LocaleSwitcher/>
            </div>
            <Main/>
        </div>
    </div>
</template>

<script>

    import Main from './components/Main.vue'
    import LocaleSwitcher from './components/LocaleSwitcher.vue'
    import Vue from 'vue'
    import {BootstrapVue, IconsPlugin} from 'bootstrap-vue'

    // Install BootstrapVue
    Vue.use(BootstrapVue)
    // Optionally install the BootstrapVue icon components plugin
    Vue.use(IconsPlugin)

    import 'bootstrap/dist/css/bootstrap.css'
    import 'bootstrap-vue/dist/bootstrap-vue.css'

    export default {
        name: 'App',
        components: {
            Main,
            LocaleSwitcher
        }
    }
</script>

<style>
    @import 'css/main.css';
</style>
