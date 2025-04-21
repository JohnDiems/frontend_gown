<template>
    <Multiselect mode="tags" :close-on-select="true" :searchable="true" :options="props.options"
        placeholder="Select option" />
</template>

<script setup lang="ts">
import Multiselect from '@vueform/multiselect'
import '@vueform/multiselect/themes/default.css'

const props = defineProps({
    options: {
        type: Array,
        required: true
    },
})
</script>