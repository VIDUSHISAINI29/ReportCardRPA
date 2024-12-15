<script setup>
import { ref } from "vue";
import Select from 'primevue/select';

const selectedAttRep = ref();
const attReport = ref([
    { name: 'The student has maintained near-perfect attendance, showing a strong commitment to their education and eagerness to learn', code: 'Excellent', bgColor: 'tw-bg-green-500' },
    { name: 'The student attends regularly with only a few absences, indicating a responsible attitude toward school', code: 'Good', bgColor: 'tw-bg-blue-500' },
    { name: 'Attendance is satisfactory, but occasional absences suggest a need for better consistency.', code: 'Satisfactory', bgColor: 'tw-bg-yellow-500' },
    { name: "Frequent absences have slightly impacted the student's learning progress.", code: 'Need Improvement', bgColor: 'tw-bg-orange-500' },
    { name: "Irregular attendance has significantly hindered the student's ability to stay updated with classroom activities.", code: 'Poor', bgColor: 'tw-bg-red-500' }
]);
</script>

<template>
  <div>
    <div class="tw-flex tw-p-2 tw-justify-center">
      <select class=" tw-p-2 tw-rounded-md tw-translate-y-0 hover:tw-translate-y-100 tw-transition-transform tw-duration-500" name="Attendence Behaviour" id="attBehave">
        <option v-for="(behaviour, index) in attReport" :key="index" :class="[' tw-h-20 tw-rounded-md', behaviour.bgColor]" value="behaviour">{{ behaviour.name }}</option>
      </select>
    </div>
    <div class="tw-flex tw-p-2 tw-justify-center">
      <select class=" tw-p-2 tw-rounded-md tw-translate-y-0 hover:tw-translate-y-100 tw-transition-transform tw-duration-500" name="Attendence Behaviour" id="attBehave">
        <option v-for="(behaviour, index) in attReport" :key="index" :class="[' tw-h-20 tw-rounded-md', behaviour.bgColor]" value="behaviour">{{ behaviour.name }}</option>
      </select>
    </div>
    <div class="tw-flex tw-p-2 tw-justify-center">
      <select class=" tw-p-2 tw-rounded-md tw-translate-y-0 hover:tw-translate-y-100 tw-transition-transform tw-duration-500" name="Attendence Behaviour" id="attBehave">
        <option v-for="(behaviour, index) in attReport" :key="index" :class="[' tw-h-20 tw-rounded-md', behaviour.bgColor]" value="behaviour">{{ behaviour.name }}</option>
      </select>
    </div>
  </div>
</template>

<style scoped>

</style>
