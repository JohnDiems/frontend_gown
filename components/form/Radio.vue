<template>
    <div class="flex items-center  py-2 grid grid-cols-2 sm:grid sm:grid-cols-2  gap-4">
        <div v-for="data in props.datas" :key="data.id" class="flex items-center">
            <input :id="data.id" type="radio" :value="data.value" :checked="data.value === modelValue"
                @change="$emit('update:modelValue', data.value)"
                class="h-4 w-5 border-gray-300 text-blue-600 focus:ring-blue-600" />
            <label :for="data.id" class="ml-3 block text-sm font-medium leading-6 text-gray-900">
                {{ data.label }}
            </label>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    datas: {
        type: Array,
        required: true,
    },
    modelValue: {
        type: [String, Boolean],
        required: true,
    },
})
</script>