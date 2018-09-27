<template>
  <div ref="jsoneditor">
    sdf
  </div>
</template>

<script>
import '@json-editor/json-editor'
export default {
  name: 'JsonEditor',
  props: {
    schema: Object,
    value: Object
  },
    data() {
      return {
          editor: null
      }
    },
    mounted() {
        console.log(this);
        const editor = new window.JSONEditor(this.$refs['jsoneditor'], {
            schema: this.schema,
            required_by_default: true
        });
        editor.setValue(this.value);
        editor.on('change', () => this.$emit('input', editor.getValue()));

        this.editor = editor
    }
}
</script>
