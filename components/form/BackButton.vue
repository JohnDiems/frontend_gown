<template>
    <button type="button" @click="props.back"
        class=" inline-flex items-center mb-1.5 gap-x-1.5 rounded-md bg-blue-50 px-4 py-2 text-sm font-semibold text-blue-600 shadow-sm hover:bg-blue-200 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
            class="-ml-0.5 h-5 w-5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5 8.25 12l7.5-7.5" />
        </svg>
        Back
    </button>
</template>

<script setup>

const props = defineProps({
    back: {
        type: Object,
        required: true,
    },
})
</script>
