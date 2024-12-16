<script setup>
import { ref, watch } from 'vue';


const selectedPara1 = ref('Selected Behaviour');
const showOptions = ref(false);
console.log('value - ',selectedPara1.value);

function triggerDropdown(params){
  selectedPara1.value = params.name;
  showOptions.value = false;
}

function triggerDropdownTrue(){
    console.log('show1 = ', showOptions.value);
 
  showOptions.value = true;
  console.log('show2 = ', showOptions.value);

}

const attReport = ref([
    { name: 'The student has maintained near-perfect attendance, showing a strong commitment to their education and eagerness to learn', code: 'Excellent', bgColor: 'tw-bg-green-500' },
    { name: 'The student attends regularly with only a few absences, indicating a responsible attitude toward school', code: 'Good', bgColor: 'tw-bg-blue-500' },
    { name: 'Attendance is satisfactory, but occasional absences suggest a need for better consistency.', code: 'Satisfactory', bgColor: 'tw-bg-yellow-500' },
    { name: "Frequent absences have slightly impacted the student's learning progress.", code: 'Need Improvement', bgColor: 'tw-bg-orange-500' },
    { name: "Irregular attendance has significantly hindered the student's ability to stay updated with classroom activities.", code: 'Poor', bgColor: 'tw-bg-red-500' }
]);
watch(showOptions, () => {
  console.log('show = ', showOptions.value);
});
console.log('show = ', showOptions.value);

</script>


<template>
  <div class="tw-p-1 tw-bg-purple-300 tw-w-72 tw-relative">
    <span @click="showOptions = true" class="tw-bg-red-200 tw-cursor-pointer tw-p-2 tw-block tw-w-full tw-rounded-md tw-shadow-lg">Selected Behaviour</span>
    <ul
    v-if="showOptions"
    class="tw-absolute tw-z-10 tw-mt-2 tw-w-full tw-bg-white tw-rounded-lg tw-shadow-xl tw-transition-all tw-duration-500 tw-ease-in-out tw-transform tw-origin-top"
    :class="showOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
    style="transform-origin: top;">
    
    <li @click="triggerDropdown(behaviour)" v-for="(behaviour, index) in attReport" :key="index" :class="['tw-w-full tw-px-4 tw-py-2', behaviour.bgColor]">{{ behaviour.name }}</li>
    </ul>
  </div>
</template>
