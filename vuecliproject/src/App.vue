<template>
    <div id="app">
        <div class="wrapper">
            <Main/>
            <SVGHome/>
        </div>
    </div>
</template>

<script>

    import Main from './components/Main.vue';
    import SVGHome from './components/SVGHome.vue'

    export default {
        name: 'App',
        components: {
            Main,
            SVGHome
        }
    }
</script>

<style>
    @import 'css/main.css';
</style>
