<template>
    <div class="relative mt-2 rounded-md shadow-sm">
        <input ref="flatpickrInput" type="text" placeholder="MM/DD/YYYY" :name="props.name" @input="updateValue($event)"
            :value="props.modelValue" :disabled="props.disabled"
            class="block w-full rounded-md border-0 px-3 h-[2.6rem] pr-10 text-blue-900 ring-1 ring-inset placeholder:text-gray-300 focus:ring-1 focus:ring-inset ring-blue-500 sm:text-sm sm:leading-6"
            aria-invalid="true" aria-describedby="email-error" />
        <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3">
            <ExclamationCircleIcon class="h-5 w-5 text-red-500" aria-hidden="true" />
        </div>
    </div>
</template>

<script setup lang="ts">
import flatpickr from 'flatpickr';
import "flatpickr/dist/flatpickr.min.css";

const props = defineProps({
    name: {
        type: String,
        required: true,
    },
    modelValue: String,
    disabled: {
        type: Boolean,
        default: false,
    },
});

const emit = defineEmits(['update:modelValue']);
const flatpickrInput = ref(null); 

onMounted(() => {
    if (flatpickrInput.value && !props.disabled) {
        flatpickr(flatpickrInput.value, {
            altInput: true,
            altFormat: "F j, Y",
            defaultDate: props.modelValue,
            onChange: (selectedDates: Date[], dateStr: string) => {
                updateValue({ target: { value: dateStr } });
            },
        });
    }
});

function updateValue(event: any) {
    emit('update:modelValue', event.target.value);
}
</script>