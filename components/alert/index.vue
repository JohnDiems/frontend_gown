<template>
    <div class="rounded-md bg-red-50 p-4">
        <div class="flex">
            <div class="flex-shrink-0">
                <XCircleIcon class="h-5 w-5 text-red-400" aria-hidden="true" />
            </div>
            <div class="ml-3">
                <h3 class="text-base font-medium text-red-800">{{ props.text }}</h3>
            </div>
        </div>
    </div>
</template>

<script setup>
import { XCircleIcon } from '@heroicons/vue/20/solid'

const props = defineProps({
    text: {
        type: String,
        default: '',
        required: true,
    },
})
</script>