<script setup>
import { ref } from "vue";

import Select from 'primevue/select';

const selectedAttRep = ref();
const attReport = ref([
    { name: 'The student has maintained near-perfect attendance, showing a strong commitment to their education and eagerness to learn', code: 'Excellent' },
    { name: ' The student attends regularly with only a few absences, indicating a responsible attitude toward school', code: 'Good' },
    { name: 'Attendance is satisfactory, but occasional absences suggest a need for better consistency.', code: 'Satisfactory' },
    { name: "Frequent absences have slightly impacted the student's learning progress.", code: 'Need Improvemnt' },
    { name: "Irregular attendance has significantly hindered the student's ability to stay updated with classroom activities.", code: 'Poor' }
]);
</script>

<template>
  <div>
   <div class="tw-flex tw-p-2 tw-justify-center">
       <Select v-model="selectedAttRep" editable :options="attReport" optionLabel="name" placeholder="Select a City" class="tw-w-56" />
   </div>
  </div>
</template>

<style scoped></style>
