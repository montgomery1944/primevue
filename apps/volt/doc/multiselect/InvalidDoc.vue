<template>
    <DocSectionText v-bind="$attrs">
        <p>Invalid state is displayed using the <i>invalid</i> prop to indicate a failed validation. You can use this style when integrating with form validation libraries.</p>
    </DocSectionText>
    <div class="card flex flex-wrap justify-center gap-4">
        <MultiSelect v-model="selectedCities" :options="cities" optionLabel="name" filter placeholder="Select Cities" :maxSelectedLabels="3" :invalid="selectedCities?.length === 0" class="w-full md:w-80" />
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import MultiSelect from '@/volt/MultiSelect.vue';
import { ref } from 'vue';

const selectedCities = ref(null);
const cities = ref([
    { name: 'New York', code: 'NY' },
    { name: 'Rome', code: 'RM' },
    { name: 'London', code: 'LDN' },
    { name: 'Istanbul', code: 'IST' },
    { name: 'Paris', code: 'PRS' }
]);

const code = ref(`
<template>
    <div class="card flex flex-wrap justify-center gap-4">
        <MultiSelect v-model="selectedCities" :options="cities" optionLabel="name" filter placeholder="Select Cities" :maxSelectedLabels="3" :invalid="selectedCities?.length === 0" class="w-full md:w-80" />
    </div>
</template>

<script setup lang="ts">
import MultiSelect from '@/volt/MultiSelect.vue';
import { ref } from 'vue';

const selectedCities = ref(null);
const cities = ref([
    { name: 'New York', code: 'NY' },
    { name: 'Rome', code: 'RM' },
    { name: 'London', code: 'LDN' },
    { name: 'Istanbul', code: 'IST' },
    { name: 'Paris', code: 'PRS' }
]);
<\/script>
`);
</script>
