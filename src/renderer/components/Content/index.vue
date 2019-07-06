<template>
    <div class="editer">
        <quill-editor ref="myTextEditor"
              v-model="content"
              @blur="onEditorBlur($event)"
              @focus="onEditorFocus($event)"
              @ready="onEditorReady($event)">
        </quill-editor>
    </div>
</template>

<script>
    import { quillEditor } from 'vue-quill-editor'
    export default {
        data() {
            return {
                content: ''
            }
        },
        methods: {
            onEditorBlur(e) {

            },
            onEditorFocus(e) {

            },
            onEditorReady(e) {

            },
        },
    }
</script>

<style lang="scss" scoped>
    .editer {
        width: 100%;
        height: 100%;
    }
    /deep/ .ql-container {
        height: 100% !important;
    }
    .quill-editor {
        width: 100%;
        height: 100%;
        // -webkit-app-region: drag;
    }
</style>
