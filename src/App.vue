<template>
    <div id="app">
        <json-editor :schema="schema" v-model="value" />
    </div>
</template>

<script>
    import JsonEditor from './components/JsonEditor'
    import schema from './webpack-config-schema'

    export default {
        name: 'app',
        components: {
            JsonEditor
        },
        data() {
            return {
                schema: schema,
                value: {}
            }
        },
        mounted() {

        },
        watch: {
            // value() {
            // }
        }
    }
</script>
