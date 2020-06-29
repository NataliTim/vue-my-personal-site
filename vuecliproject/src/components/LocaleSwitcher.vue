<template>
    <div>
        <p>LocaleSwitcher text</p>
        <ul>
            <li v-for="locale in locales" :key="locale" @click="switchLocale(locale)">
                {{locale}}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'LocaleSwitcher',
        data() {
            return {
                /* locales: ['en','ru']*/
                locales: process.env.VUE_APP_I18N_SUPPORTED_LOCALE.split(',')
            }
        },
        methods: {
            switchLocale(locale) {
                if (this.$i18n.locale !== locale) {
                    this.$i18n.locale  = locale;              }
            }
        }
    }
</script>

<style scoped>

</style>