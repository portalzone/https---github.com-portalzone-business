<script setup>
import { onMounted, ref } from 'vue';
defineProps(['modalValue', 'options']);

const model = defineModel({
    type: String,
    required: true,
});

defineEmits(['update:modalValue']);

const input = ref(null);

onMounted(() => {
    if (input.value.hasAttribute('autofocus')) {
        input.value.focus();
    }
});

defineExpose({ focus: () => input.value.focus() });
</script>

<template>
    <select
        class="border-gray-300 focus:border-indigo-500 focus:ring-indigo-500 rounded-md shadow-sm"
        v-model="model"
        ref="input">
        <option v-for="op in options" :key="op.i" :value="op.id" name="department_id">{{ op.name }}</option>
    </select>
    
</template>


<!-- <script setup>
import { onMounted, ref } from 'vue';

defineProps(['modalValue', 'options']);

defineEmits(['update:modalValue']);

const model = defineModel({
    type: String,
    required: true,
});

const input = ref(null);

onMounted(() => {
    if (input.value.hasAttribute('autofocus')) {
        input.value.focus();
    }
});

defineExpose({ focus: () => input.value.focus() });
</script>

<template>
    <select
        class="border-gray-300 focus:border-indigo-500 focus:ring-indigo-500 rounded-md shadow-sm"
        :value="modelValue"
        @change="$event=> $emit('update:modalValue', $event.target.value)"
        ref="input">
    <option v-for="op in options" :key="op.i" :value="op.id" name="department_id">{{ op.name }}</option>
    
</select>
</template> -->
<!-- <script setup>
import { onMounted, ref } from 'vue';

defineProps(['modalValue', 'options']);

defineEmits(['update:modalValue']);

const model = defineModel({
    type: String,
    required: true,
});

const input = ref(null);

onMounted(() => {
    if (input.value.hasAttribute('autofocus')) {
        input.value.focus();
    }
});

defineExpose({ focus: () => input.value.focus() });
</script>

<template>
    <select
        class="border-gray-300 focus:border-indigo-500 focus:ring-indigo-500 rounded-md shadow-sm"
        :value="modelValue"
        @change="$emit('update:modalValue', $event.target.value)"
        ref="input"
    >
        <option v-for="op in options" :key="op.id" :value="op.id">{{ op.name }}</option>
    </select>
</template> -->
