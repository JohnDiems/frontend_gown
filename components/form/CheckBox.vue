<template>
    <div class="flex items-center py-2 grid grid-cols-2 sm:grid sm:grid-cols-2 gap-4">
        <div v-for="data in props.datas" :key="data.id" class="flex items-center">
            <input :id="data.id" type="checkbox" :value="data.value" :checked="isChecked(data.value)"
                @change="toggleSelection(data.value)"
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
        type: Array,
        required: true,
    },
})

const emit = defineEmits(['update:modelValue'])

function isChecked(value) {
    return props.modelValue.includes(value);
}

function toggleSelection(value) {
    const selectedValues = [...props.modelValue]
    const index = selectedValues.indexOf(value)
    if (index === -1) {
        selectedValues.push(value)
    } else {
        selectedValues.splice(index, 1)
    }
    emit('update:modelValue', selectedValues)
}
</script>
