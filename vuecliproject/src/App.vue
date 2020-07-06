<template>
    <div id="app">
        <div class="wrapper">
            <Main/>
        </div>
    </div>
</template>

<script>

    import Main from './components/Main.vue'

    export default {
        name: 'App',
        components: {
            Main
        }
    }
</script>

<style>
    @import 'css/main.css';
</style>
