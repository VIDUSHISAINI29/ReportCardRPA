<script setup>
import { ref, watch } from 'vue';


const attPlaceholder = ref('Select Attendence Record');
const academicPlaceholder = ref('Select Academic Record');
const selectedAttReport = ref('Selected Attendence Report ');
const selectedAcademicReport = ref('Selected Academic Report ');
const showOptions = ref(false);
const showOptions2 = ref(false);

function triggerDropdown(params){
  const modifyValue = params.name.slice(0,30) + '...';
  attPlaceholder.value = modifyValue;
  selectedAttReport.value = params.name;
  showOptions.value = false;
}
function triggerDropdown2(params){
  const modifyValue = params.name.slice(0,30) + '...';
  academicPlaceholder.value = modifyValue;
  selectedAcademicReport.value = params.name;
  showOptions2.value = false;
}

function triggerDropdownTrue(){
    console.log('show1 = ', showOptions.value);
 
  showOptions.value = !showOptions.value;
  console.log('show2 = ', showOptions.value);
}
function triggerDropdownTrue2(){
  showOptions2.value = !showOptions2.value;
}

const attReport = ref([
    { name: 'The student has maintained near-perfect attendance, showing a strong commitment to their education and eagerness to learn', code: 'Excellent', bgColor: 'tw-bg-green-200 hover:tw-bg-green-400' },
    { name: 'The student attends regularly with only a few absences, indicating a responsible attitude toward school', code: 'Good', bgColor: 'tw-bg-blue-200 hover:tw-bg-blue-400' },
    { name: 'Attendance is satisfactory, but occasional absences suggest a need for better consistency.', code: 'Satisfactory', bgColor: 'tw-bg-yellow-200  hover:tw-bg-yellow-400' },
    { name: "Frequent absences have slightly impacted the student's learning progress.", code: 'Need Improvement', bgColor: 'tw-bg-orange-200 hover:tw-bg-orange-400' },
    { name: "Irregular attendance has significantly hindered the student's ability to stay updated with classroom activities.", code: 'Poor', bgColor: 'tw-bg-red-200 hover:tw-bg-red-400' }
]);

const academicReport = ref([
    { 
        name: 'The student demonstrates exceptional academic skills, consistently exceeding expectations across all subjects. They actively engage in class discussions, complete assignments with precision, and showcase a thorough understanding of complex concepts. Their ability to think critically and solve problems creatively sets them apart.', 
        code: 'Excellent', 
        bgColor: 'tw-bg-green-200 hover:tw-bg-green-400' 
    },
    { 
        name: 'The student has a strong academic foundation and performs well in most areas. They actively participate in class and complete assignments on time. Occasionally, they may need support with more advanced topics, but their overall performance reflects dedication and hard work.', 
        code: 'Good', 
        bgColor: 'tw-bg-blue-200 hover:tw-bg-blue-400' 
    },
    { 
        name: 'The student has a satisfactory understanding of the core subjects. While they perform well in familiar topics, they sometimes face challenges in new or complex areas. With consistent effort and additional practice, they have the potential to enhance their skills and performance.', 
        code: 'Satisfactory', 
        bgColor: 'tw-bg-yellow-200 hover:tw-bg-yellow-400' 
    },
    { 
        name: "The student struggles with certain subjects and requires focused guidance to improve their academic performance. They may lack confidence in applying concepts and need encouragement to actively participate in class. Regular practice and personalized attention could help them overcome these challenges.", 
        code: 'Needs Improvement', 
        bgColor: 'tw-bg-orange-200 hover:tw-bg-orange-400' 
    },
    { 
        name: "The student's academic performance is significantly below expectations. They face difficulty understanding fundamental concepts and often need substantial support to complete tasks. A structured intervention plan, combined with consistent encouragement, is essential to help them progress.", 
        code: 'Poor', 
        bgColor: 'tw-bg-red-200 hover:tw-bg-red-400' 
    }
]);

watch(showOptions, () => {
  console.log('show = ', showOptions.value);
});
console.log('show = ', showOptions.value);

</script>


<template>
 <div class="tw-w-full tw-flex">
  <div class="tw-w-3/4 tw-bg-[#E0F7FA] tw-p-2 ">
    <div class="tw-w-full tw-flex tw-flex-col tw-gap-3 tw-border-4 tw-p-1 tw-border-[#FF8A80]">
      <span class="tw-block">{{ selectedAttReport }}</span>
      <span class="tw-block">{{ selectedAcademicReport }}</span>
    </div> 
  </div>
  <div class="tw-w-1/4 tw-bg-white tw-p-2">
    <div class="tw-p-1  tw-w-72 tw-relative tw-flex tw-flex-col">
      <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">Select Attendence Report</span>
     <span @click="triggerDropdownTrue" class="tw-bg-red-200 tw-text-[15px] tw-cursor-pointer tw-p-2 tw-block tw-w-full tw-rounded-md tw-shadow-lg">{{attPlaceholder}}</span>
      <ul
    
      class="tw-absolute tw-z-10 tw-mt-[70px] tw-w-[97%] tw-p-1 tw-bg-white tw-rounded-lg tw-shadow-xl tw-gap-1 tw-flex tw-flex-col tw-transition-transform tw-duration-500 tw-ease-in-out  tw-transform tw-origin-top"
      :class="showOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
      style="transform-origin: top;">
    
      <li @click="triggerDropdown(behaviour)" v-for="(behaviour, index) in attReport" :key="index" :class="['tw-w-full tw-rounded-lg tw-px-4 tw-py-2 tw-cursor-pointer tw-transition-colors tw-duration-200', behaviour.bgColor]">{{  behaviour.name.slice(0,50) + '...'  }}</li>
      </ul>
    </div>
    <div class="tw-p-1  tw-w-72 tw-relative tw-flex tw-flex-col">
      <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">Select Attendence Report</span>
     <span @click="triggerDropdownTrue2" class="tw-bg-red-200 tw-text-[15px] tw-cursor-pointer tw-p-2 tw-block tw-w-full tw-rounded-md tw-shadow-lg">{{academicPlaceholder}}</span>
      <ul
    
      class="tw-absolute tw-z-10 tw-mt-[70px] tw-w-[97%] tw-p-1 tw-bg-white tw-rounded-lg tw-shadow-xl tw-gap-1 tw-flex tw-flex-col tw-transition-transform tw-duration-500 tw-ease-in-out  tw-transform tw-origin-top"
      :class="showOptions2 ? 'tw-scale-y-100' : 'tw-scale-y-0'"
      style="transform-origin: top;">
    
      <li @click="triggerDropdown2(behaviour)" v-for="(behaviour, index) in academicReport" :key="index" :class="['tw-w-full tw-rounded-lg tw-px-4 tw-py-2 tw-cursor-pointer tw-transition-colors tw-duration-200', behaviour.bgColor]">{{ behaviour.name.slice(0,50) + '...' }}</li>
      </ul>
    </div>
  </div>
 </div>
</template>
